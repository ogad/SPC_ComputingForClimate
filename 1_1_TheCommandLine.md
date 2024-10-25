< [Introduction](./README.md) | [Processes](./1_2_Processes.md) >

# 1.1 The command line
Text as both input and output—a product of early computing infrastructure.

## Introduction
A *shell* provides the command line interface to launch *commands*, and basic tools like passing data between commands or wildcard matching for filenames.
The shell passes these commands to the *kernel*, which manages the computer's resources and command execution.
The command line is still the primary way to access shared computing resources (like the HPC or the Group computers) or cloud computing resorces/containers (which are common in industry), and can be an effective way to work on your own machines.

Linux and macOS come with a "Unix-style shell"—this is the kind of shell that you'll find on remote computers too.
Windows comes with its own "DOS-style" command line interface, but can now run a "subsystem for Linux" which provides a Unix-style shell.

## Using commands
The terminal will look something like this:
![An empty prompt](./img/empty_prompt.png)

The text is the *prompt*, here it contains the username, hostname, current directory, and `%`.
The `%` character is just a marker to indicate the point at which you can begin to type.
The prompt can be customised, which is one of many ways you can customise you command line interface.

Commands can be run after the prompt.
The command consists of the programme name, followed by any **options** and then any **arguments**.
Most commands look something like this:
```bash
command -options arguments
```

Most of the time, options are specified by a single character preceded by a dash, for example `-v`.
Many commands have *long form* versions of the options too—which have two dashes, for example `--verbose`.
You can also chain the short forms for many commands, for example `-lah` is equivalent to `-l -a -h`.

For the "shell builtin" commands, you can use the command `help` to get some information about what options you might try.
The tool [`tldr`](https://tldr.sh/) is worth trying out if you're spending some serious time getting to know the command line—it provides clear documentation pages into a nice format with examples.
The hardcore documentation tool is `man`—this can be used to explore

## Navigating the file system
The file systems on Unix-style machines have some differences to Windows—they're more similar to Macs.
The root directory (at the base of the file system) is "`\`".
All file locations in the file system begin with this.

File paths can be specified as *absolute* (meaning relative to the root directory, so beginning with `\`) or *relative* (meaning starting from the current "working directory").
Relative paths begin straight away with a file or directory name.
You can also specify paths to start from your "home" directory using the `~` character.
The home directory is your personal space, where you can store your own files, configurations, and applications.


Some basic commands give you a way to interact with the file system:
- [`pwd`](https://tldr.inbrowser.app/pages/common/pwd) Display the name of the current "working directory".
- [`cd`](https://tldr.inbrowser.app/pages/common/cd) Change the current working directory.
- [`ls`](https://tldr.inbrowser.app/pages/common/ls) List the files in the current working directory.

Files beginning with a `.` are "hidden".
By default, they are not shown in lists of file names, or in graphical interfaces.
Using `ls`, the `-a` option includes these files.
Running `ls -a`, we see two special hidden files: "`.`", which refers to the current folder, and "`..`", which refers to the parent folder.

You can manipulate files:
- [`mv`](https://tldr.inbrowser.app/pages/common/mv) Move or rename a file.
- [`cp`](https://tldr.inbrowser.app/pages/common/cp) Copy a file.
- [`rm`](https://tldr.inbrowser.app/pages/common/rm) Delete files. (Be careful! There's no "Bin" to recover files, and wildcards can cause lots of files to be lost).

And directories:
- [`rmdir`](https://tldr.inbrowser.app/pages/common/rmdir) Delete directories.
- [`mkdir`](https://tldr.inbrowser.app/pages/common/mkdir) Make a directory.

## Creating, viewing, and editing files
You can use *redirection* to send command output to a file.
This is done by adding `> path/to/file` after a command.
This overwrites the file, using two `>` symbols (i.e. `>> path/to/file`) will append to an existing file.

Other commands useful for file creation are:
- [`touch`](https://tldr.inbrowser.app/pages/common/touch) Create an empty file.
- [`echo`](https://tldr.inbrowser.app/pages/common/echo) Displays its argument. Can be useful when applied in conjuction with redirection.

Files can be viewed by displaying their contents:
- [`cat`](https://tldr.inbrowser.app/pages/common/cat) Display the contents of a file.
- [`less`](https://tldr.inbrowser.app/pages/common/less) Show the file contents using a "pager".

The command line can also be used to lauch editors:
- `nano` A basic text editor
- `vim` A very powerful, but more complicated text editor designed to be super fast when you use the keyboard. (see also it's predecessor `vi` and the newer "neovim").
- `emacs` Another powerful text editor which is widely customisable.
Experienced users will tend to choose one of either `vim` or `emacs` and use it frequently.
You can also install command line interfaces for graphical IDEs (like VS Code) and launch them from the command line.

## Piping
Command outputs to another command as input.
The pipe symbol (`|`) after a command pipes its "standard output", often called `STDOUT`, to the next command's "standard input", `STDIN`.

For example, to find the number of files in a folder we could pipe the output from `ls -1` (list the files in the working directory with one file on each line) to `wc -l` (count the number of lines in the input).
Altogether, the command to run would be `ls -l | wc -l`.
Note that STDIN isn't the same as the command's arguments—it's more often the contents of the file you'd pass as an argument.
This also works well for viewing large output using a pager like `less` instead of viewing them all in the command line (i.e. `ls -1 | less`).

Useful commands for making good use of this include:
- [`wc`](https://tldr.inbrowser.app/pages/common/wc) Count words in the input (or lines, etc.).
- [`uniq`](https://tldr.inbrowser.app/pages/common/uniq) Show unique lines from the input.
- [`sort`](https://tldr.inbrowser.app/pages/common/sort) Sort the input.

## Shell scripting
As well as excuting commands in the command line, you can write shell scripts.
You can do this by writing a file containing a list of commands and passing it to the `bash` command (or your shell of choice).
Usually, these are given the file extension `.sh`.
Shell scripts can contain any number of bash commands, and are useful for running e.g. sequences of python scripts.

Shell scripts can also be made executable (i.e. runnable by quoting the pathname like a command) by beginning with a "shebang":
```bash
#!/bin/bash
```
You then also need to change the permissions of the file to be executable, read more in [1.3 The file system](./1_3_FileSystem.md).


## Sources
- [Ubuntu Tutorials: The Linux Command Line for Beginners](https://ubuntu.com/tutorials/command-line-for-beginners)
- [William Smith, The Linux Command Line](https://linuxcommand.org/tlcl.php)


< [Introduction](./README.md) | [Processes](./1_2_Processes.md) >
