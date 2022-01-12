# Advanced Shells 


## Shell Programming

Once you have a set of commands or steps you perform frequently enough, you might find it useful to put into a bash script, including:

* Data collection scripts for mining data; data processing and cleaning scripts.
* Set up a local server, vms or containers, or anything else needed to test or run a complex application.
* Provision and deploy an application on a remote server.

While you do these all in the context of a interactive shell, some of the following are particular useful for writing multiple lines of scripts.

Useful conditionals and loops:

```bash
if command; then
   commands
fi

[ -z "$var" ] && echo "var is undefined" || echo "var is defined"

while command; do
  commands
done
```

Storing variables and results of commands; referencing variables

```bash
e=expansion
e=$(command)
$e
echo "result is: $e"
```

**Activity**: Imagine you wanted to write a "dead" startup checker using the product hunt data. Using the script below, you would be able check if a startup's url was still alive. Create an executable file called 'checker.sh', that is `chmod +x checker.sh`.

Download data with `wget`.

```bash|{type:'command', stream: true}
wget -nc https://s3-us-west-2.amazonaws.com/producthunt-downloads/ph-export--2016-04-01.tar.gz --show-progress --progress=bar:force 2>&1
```

Create a directory to store the tar file contents

```bash|{type:'command'}
mkdir product-hunt 
```

Extract the archive and verify csv files exist inside the product-hunt folder.

```bash|{type:'command'}
tar -zxvf ph-export--2016-04-01.tar.gz -C product-hunt/
ls product-hunt/
```

```bash|{type: 'file', path: 'checker.sh', permission: '+x', range: {start:3, end: 6}}
#!/bin/bash

# Print error message and exit with error code 1
function die {
    echo "$1"
    exit 1
}

# Check the number of arguments
[ $# -ge 1 ] || die "usage: $0 <posts-file> [num]"

# Assign commmand line parameters
POSTS_FILE=$1
# If no number is provided, use default value of 10
NUMBER=$([ -z "$2" ] && echo "10" || echo $2)

# Make sure that the posts file exists
[ -f $POSTS_FILE ] || die "Input file ($POSTS_FILE) not found"

echo "Checking first $NUMBER in $POSTS_FILE"

# Skip first line (delete with sed), and retrieve first n results with head.
RESULTS=$(sed 1,1d $POSTS_FILE | head -n $NUMBER)

# Loop over each line of input (provided below with <<< "$RESULTS")
while read -r line; do

    #Retrieve the product name and url from line.
    name=$(echo $line | cut -f3 -d ';')
    redirect_url=$(echo $line | cut -f9 -d ';')

    # Make a request to the url and store the reported status code.
    HTTPCODE=$(curl -L -s -o /dev/null -w "%{http_code}" $redirect_url)

    # Print the results. 404 equals dead link!
    DEAD=$([ "$HTTPCODE" == "404" ] && echo " (💀)")
    echo "$name$DEAD: $redirect_url => $HTTPCODE"

done <<< "$RESULTS"
```

Run the script:

```bash|{type:'command', shell: 'bash'}
./checker.sh product-hunt/posts--2016-04-01_14-36-24-UTC.csv 3
```

You should see output like this:

```
Checking first 3 in product-hunt/posts--2016-04-01_14-36-24-UTC.csv
We Are Heroes (💀): http://www.producthunt.com/l/b3443c7ac79b50 => 404
Tesla Model 3: http://www.producthunt.com/l/3843d5a8440dc8 => 200
Captain Strike (💀): http://www.producthunt.com/l/45fad46fe3f810 => 404
```

**Exercise**: Try running the script with a larger number of posts to check. How did it go?

**Exercise**: Go through the script line-by-line with a partner. Do you understand what each line is doing? Which ones are confusing?

## Weird but useful features and commands in bash

### Heredoc

In some situations, you might need to send multi-line content as input to a command or to store as a file. `heredoc` is an input mechanism that allows you to enter in text (interactively or in a script), until a delimiter string is reached `'END_DOC'`.  The single quotes in the heredoc marker is important---that will make sure your script commands are properly escaped.

```bash|{type:'command', shell: 'bash'}
cat << 'END_DOC' > .functions
mostUsed()
{
history | awk '{CMD[$2]++;count++;}END { for (a in CMD)print CMD[a] " " CMD[a]/count*100 "% " a;}' | grep -v "./" | column -c3 -s " " -t | sort -nr | nl |  head -n10    
}
END_DOC
```

Load the defined function. Then we can see which command you run the most.

```bash|{type:'command', shell: 'bash'}
source .functions
mostUsed
```

Heredoc can also be useful for running command on input you'd like to type in manually or paste from your clipboard and don't want to bother placing in a file. In this case, we can omit the single quotes for our heredoc marker `EOF`, since we're only processing simple text without bash commands.


Count the number of lines, words, and characters in text:

```bash|{type:'command', shell: 'bash'}
cat << EOF | wc
Lieutenant-General Sir Adrian Paul Ghislain Carton de Wiart (5 May 1880 – 5 June 1963), 
was a British Army officer of Belgian and Irish descent. He fought in the Boer War, World War I, and World War II, 
was shot in the face, head, stomach, ankle, leg, hip and ear, survived a plane crash, tunneled out of a POW camp, 
and bit off his own fingers when a doctor wouldn’t amputate them. 
He later said "frankly I had enjoyed the war."
EOF
```

### dd

`dd` can be useful for cloning disk drives or disk images, creating test data, and just generally wrecking havoc on disks (which could be useful for chaos engineering experiments).

Create a 1MB file with zeros.

```bash|{type:'command', failed_when:'exitCode!=0'}
dd if=/dev/zero of=zeros.txt count=1024 bs=1024
```

Create a 20K file with random bytes.

```bash|{type:'command', failed_when:'exitCode!=0'}
dd if=/dev/urandom of=random.txt bs=2048 count=10
```

### expect

<!-- Helpful: https://superuser.com/questions/1166920/how-do-i-send-the-stdout-of-a-command-to-an-expect-input -->

Expect the unexpected. If you need to automate a command which could prompt for input, then you can use `expect` to help respond to that input.

Just as a simple example, if you ran this code `python -c "print( input('Enter value: ') )"`, it will wait around until you typed something, which could be a problem if you're doing this 1000s of times or run in an automation script.

By using expect, you can create scripts that automatically response to prompt inputs.

Warning: `expect` is not directly available on Windows.

```bash|{type:'command', shell: 'bash'}
expect <<- END
    spawn python -c "print( input('Enter value: ') )"
    expect {
        "Enter value: " { send "42\r"}
    }
    interact
END
```

Expect is pretty tricky to learn how to use properly, but it is a nice trick to hold on to in case you need it one day.

### Traps

Using traps for [resource cleanup](http://redsymbol.net/articles/bash-exit-traps/), or implementing a singleton process.





Install simple server.
```bash|{type: 'command'}
npm install http-server -g
```

Save the following in 'server.sh' and make it executable.

```bash|{type: 'file', path: 'server.sh', permission: '+x'}
#!/bin/bash

LOCKFILE=510-bash.lock

# Exit if lockfile 
[ -f $LOCKFILE ] && echo "Lockfile is in use. Exiting..." && exit 1 

# Upon exit, remove lockfile.
function cleanup
{
    echo "cleaning up"
    rm -f $LOCKFILE
    exit 0
}

# Initiate the trap
trap cleanup EXIT SIGINT

# Create lockfile
touch $LOCKFILE

# Simple web server (listen on port 8888)
# while true; do { echo -e "HTTP/1.1 200 OK\n\n$(date)"; } | nc -l 8888; done
http-server -p 8888
```

This will run a simple webserver, spawned in its own process.

```bash|{type:'command', shell: 'bash', spawn: true}
./server.sh
```

To see what's being served, in a new terminal window, run:

```bash|{type:'command'}
wget -qO- localhost:8888
```

If you try running `./server.sh` in another terminal, it should prevent you from running again.

```bash|{type:'command', shell: 'bash'}
./server.sh
```

Let's stop our server (Windows): *Note*: this is a nice example where powershell's scripting powers come into good use.
```bash|{type:'command', platform: 'win32', shell: 'powershell'}
Get-CimInstance Win32_Process -Filter "CommandLine LIKE '%http-server%'" | Remove-CimInstance
```

Let's stop our server (Mac/Linux)
```bash|{type:'command'}
pkill -f 'http-server'
```

Let's confirm lock file is removed:

```bash|{type:'command'}
test -f 510-bash.lock && echo "file exists." && exit 1 || echo "file is gone."
```

## Remote connections

In many situations, you may find that you need to run commands for development or debugging on remote servers. Most likely, you will initate this connection over a ssh connection.

### Running remote commands

`ssh` allows you to execute commands on a remote server, such as these commands to install nodejs:

```
ssh vagrant@192.168.33.10 sudo apt-get update && sudo apt-get install nodejs -y
```

**Persistance**: If you need to change directories, you will need to do it in the same command: `cd App/ && cmd`.

Otherwise, your next command will start back in the same original directory. Because you're sending commands over ssh, this is done in `exec` mode. In exec mode, each command will be executed in its own context and lose many of the shell's functionality. ssh can operate in a `shell`, `exec`, or `subsystem` [channels](https://stackoverflow.com/questions/6770206/what-is-the-difference-between-the-shell-channel-and-the-exec-channel-in-jsc). When using a shell channel, you can interactively send commands like a normal shell. A cd operation will persist in this case. 

Finally, you can emulate some parts of a terminal using `-t or -tt` as well as combining with heredoc to input a multi-line script.

### tmux

When issuing a long running command (package installation, build job), you may find your connection drop, which could result in termination of your command!

A useful strategy to avoid this is to use a session manager, such as `screen` or `tmux`. These tools will allow you to create sessions that will persist on the server, allowing you to run commands, disconnect, and return again.

Here is a useful [reference](http://hyperpolyglot.org/multiplexers).