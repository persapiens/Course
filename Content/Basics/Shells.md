[Setup](Setup.md#setup) | [Shells](Shells.md#shells) |  [Git](Git.md#git) | [Markdown and IDEs](MarkdownEditors.md#markdown) |  [Virtual Environments](Environments.md#environments) | [Task Management](OnlineTools.md#online-tools)

# Shells

A shell is a computing environment where commands can be interpreted, evaluated, and its output displayed (i.e., an instance of a read–eval–print loop (REPL)). A good shell provides access to a rich set of commands and allows simple programming of commands, which can be used to create powerful scripts and tools.

```bash|{type:'command'}
ls -R | grep ":$" | sed -e "s/:$//" -e "s/[^-][^\/]*\//--/g" -e "s/^/ /" -e "s/-/|/"
```

**But with great power comes great bullshittery**. Commands and their options can be [terse, inconsistent, and difficult to learn](http://www.pgbovine.net/command-line-bullshittery.htm). A steep learning curve often prevents novices from enjoying the eventual payoff. If you've hardly used a command line environment before, you might want to go review this more thorough tutorial:
[software carpentry: shell-novice](http://swcarpentry.github.io/shell-novice/index.html)---this page is more of a discussion of common tasks and mistakes, advanced topics, and resources.

You may also want to reference the online book, [the Unix Workbench](https://seankross.com/the-unix-workbench/).

## Shell Basics

### Commands

99% of the reason you use shells is to run useful commands.

##### Essential commands.

* **`ls`**: list content of a directory.
* **`cd`**: change directories to a new path.
* **`mkdir`**: make a new directory.
* **`pwd`**: output current directory
* **`cp`**: copy files
* **`rm`**: rm files
* **`touch`**: make a new file/update status**
* **`cat`**: output the contents of a file.
* **`head`**: output the first lines of a file.
* **`tail`**: output the last lines of a file.
* **`grep`**: search files for a key phrase.
* **`wget`**: retrieve file from the web.
* **`cut`**: extract output of a file (columns)
* **`awk`** and **`sed`**: Magic commands for extracting, searching, and transforming content.

##### Combining commands

Command can run sequentially or conditionally:

```bash
command1 ; command2
(command1 ; command2) # in a sub-shell
command1 || command2  # do command2 only if command1 fails
command1 && command2  # do command2 only if command1 succeeds
```

*Note*: In Windows, `;` does not work in Cmd, but does in Powershell. Use `&&` for the most portable operation.

Try running this command that combines these shell commands.

```bash|{type: 'command'}
echo "Hello World" > shells-test.txt && cat shells-test.txt
```

Now, try using the `||` operator. 

```bash|{type: 'command', }
cat shells-test.txt || echo "backup plan"
```

See what happens in this case.

```bash|{type: 'command', failed_when: "!stdout.includes('backup plan')"}
cat filedoesnotexist.txt || echo "backup plan"
```

##### Command I/O

The UNIX shell commands push data from sources through filters along pipes. Normally, each command runs as a process and reads and writes data the following way:

* **Standard input (stdin)**: get information from keyboard.
* **Standard output (stdout)**: write information as output to console.
* **Standard error (stderr)**: write error information as output to console.

Pipes and redirects change stdin and stdout from default sources. For example, we can change the stdin of a process to be piped from the output of another process. Or rather than printing to the console, we can get a process to write to a file.

```bash
command              # default standard in and standard out
command < inputFile  # redirect of inputFile contents to command as standard in
command > outputFile # redirect command output to outputFile as standard out
command1 | command2  # pipes output of command1 as standard in to command2
```

**Neat trick**: Copy the value of a file into your clipboard!

Windows: `clip < file.txt` Mac: `pbcopy < file.txt` 

```bash|{type:'command', platform: 'darwin'}
pbcopy < ~/.ssh/id_rsa
```

```bash|{type:'command', platform: 'win32'}
clip < %HOME%/.ssh/id_rsa
```

### 📒 Online Exercise

Click the following to start the exercise.

<a href="https://devops.docable.cloud/chrisparnin/v/61deeb28033cc264a107b356">
<img src="resources/imgs/data-science-notebook-preview.png">
</a>


## Resources

### Bite Size Command Line Zine

You might find Julia Evan's zine useful: [Bite Size Command Line!](https://jvns.ca/blog/2018/08/05/new-zine--bite-size-command-line/).

Here is an example for the `lsof` command. More examples can be found [here](https://twitter.com/i/moments/1026078161115729920).

![lsof](https://pbs.twimg.com/media/DjFb_FPX4AAOwpa?format=jpg&name=medium)

### Command Line Fu

A list of command line examples for interesting tasks:  
http://www.commandlinefu.com/commands/browse

Create a graphical directory tree from your current directory.
```
ls -R | grep ":$" | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/ /' -e 's/-/|/'
```

### Explain shell

What does `tar -zxvf ph.tar.gz` do?

http://explainshell.com/explain?cmd=tar+-zxvf

![image](https://cloud.githubusercontent.com/assets/742934/15635713/8fc9cf7e-25b4-11e6-957e-0bb03756b9fb.png)
