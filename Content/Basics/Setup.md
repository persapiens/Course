# Setup

To successfully build software, you need a properly configured environment with a variety of tools. To help us get started, we will we install some tools, package managers, that make it a little easier to configure systems. 

Whether you're a Mac, Windows, or Linux user---you should be able to find a way to be productive with the tools from this workshop. However, there may be specific tweaks, issues, and accomodatations you may have to make based on your platform.

### 1. Finding your terminal.

* **Mac**: you can run the Terminal in Applications and pin to your Dock.

* **Windows**: You access a shell in several ways. You can right click on the Windows Icon in the Task Bar and open a terminal window. You can also type in the name of the shell program in the search bar (e.g., Cmd/Powershell). 

*Tip*: IDES, such as VS Code provide easy access to a terminal (View ⇨ Terminal).

### 2. Privileged commands

Some commands require adminstrative or super user privileges.

* **Mac/Linux**: To access a privileged shell, you simply can run `su` or prepend a command with `sudo`. `sudo` will cache your password, typically for 5 minutes, after successfully running a command. To avoid typing a password at all, you may add your user to `/etc/sudoers`---note it is recommended you make changes to this file using the special utility: [visudo](https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file).

* **Windows**. If you need to run a command with admin, you must start a shell with admin privilege. There is typically an admin command shell available in the menu when right clicking the Windows Icon on the Task Bar. You can also get one from right clicking the Cmd executable in the search bar.

   *Tip*: If opening up a cmd shell in admin mode, make sure you do not perform operations, such as `git clone` in your current directory (`C:\WINDOWS\system32`). Otherwise, you will be writing to a location that only admin will have access to which will make it difficult to run the commands/tasks you are intending on doing.

### 3. Deciding on a Terminal/Shell for Windows



### 4. Package Managers.

**An installation philosophy**
> *Avoid manual installation, automate with package managers!*

When possible, using a package manager can allow you to automate and streamline the installation of tools. Instead of hunting down the right website, finding the right version and dowload link, then clicking through an installation wizard---you let the package manager take care of all those manual steps for you! 

*Tip*: Later on, the ability to automate the installation of software environments becomes important in later stages of software development, such as continuous integration, or deployment.

We will learn how to use package managers to help use manage our system.


### 5. Path and Environment Variables.

## Environment Variables

Environment variables are dynamically configurable elements that are available to processes on your system.

Mac/Linux: `echo $PATH`
Windows: `echo %PATH%`

A common problem with shells is that changing your `PATH` or other environment variables after an installation/OS GUI change will not affect any currently open shells. You either have to manually refresh the shell or open a new one. 

##### Setting Environment Variables (Windows)

In addition to editing environment variables in your desktop manager GUI, you can also set environment variables in your shell.

In Windows, you can use `set` and `setx` to update environment variables. `set` will update environment variables in your current shell instance, but that will be lost after the shell closes. Using `setx`, you can permanently, set an environment variable for the user or system (use `setx /m`). See the [documentation](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/setx) for more information.

```bash|{type:'command'}
set DEBUG_MODE=true
echo "Current DEBUG_MODE=%DEBUG_MODE%"
```

Tip: One limitation of using setx is that it cannot store values longer than 1024 characters.

##### Setting Environment Variables (Mac/Linux)

In bash/*sh environments, you can set temporary environment variables in two ways:

Like `set`, you can define a variable just for your shell session, but not for running programs.

```bash|{type:'command'}
DEBUG_MODE=true
echo $DEBUG_MODE
node -e 'console.log(`DEBUG_MODE=${process.env.DEBUG_MODE}`);'
```

##### Scoping

You can also define a variable that will only exist inside a subprocess spawned from the shell. **This may not behave the way you expect**!

```bash|{type:'command', shell:"bash"}
DEBUG_MODE=true echo "DEBUG_MODE=$DEBUG_MODE"
DEBUG_MODE=true node -e 'console.log(`DEBUG_MODE=${process.env.DEBUG_MODE}`);'
```
A blank is printed out because `$DEBUG_MODE` is expanded before the process executing the echo command is started. On the other hand, inside the node program, the process inherits the shell's environment variables, including the DEBUG_MODE variable.

Finally, you can enable access to an environment variable for all processes and subprocesses started in the shell by using `export VAR=VALUE`

```bash|{type:'command'}
export DEBUG_MODE=true
echo $DEBUG_MODE
node -e 'console.log(`DEBUG_MODE=${process.env.DEBUG_MODE}`);'
```

> *Permenant environment variables are actually more tricky in Mac/Linux shells!*

When a shell is initialized, several startup scripts are run for customization and initialization. If you want to make a variable always available, a common strategy is to locate one of these initialization scripts (typically in your home directory, and editing them to run your commands on startup). Common locations include: `~/.profile`, or `~/.bashrc`. The symbol `~`, is a shortcut for your home directory: `/home/<user>`.

To summarize (Mac/Linux):

* Use `export VAR=VALUE` to enable a variable to be seen by all executed commands.
* Use `VAR=VALUE` for a variable only available in the shell.
* Use `VAR=VALUE <command>` for a variable only available to that command.
* Set permenant variables inside a start script such as `~/.bashrc`.


5. Exercise: Customize your prompt
5. Exercise: Practice install packages.