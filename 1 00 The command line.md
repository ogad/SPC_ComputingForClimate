# The command line
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

## Navigating the file system
The most basic commands give you a way to interact with the file system:
- `pwd` Print the name of the current "working directory".
- `cd` Change the current working directory.
- `mv` Move a file.
- `cp` Copy a file.
- `rm` Delete files.
- `rmdir` Delete directories.


## Sources
- [Ubuntu Tutorials: The Linux Command Line for Beginners](https://ubuntu.com/tutorials/command-line-for-beginners)
- [William Smith, The Linux Command Line](https://linuxcommand.org/tlcl.php)
