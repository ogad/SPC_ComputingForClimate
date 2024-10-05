< [The Command Line](./1_1_TheCommandLine.md) | [The File System](./1_3_FileSystem.md) >

# 1.2 Processes
Processes are managed by the kernel—they're how the computer keeps track of tasks on the go.

## `htop`
`htop` is a tool for viewing the processes running on a computer and the resources currently used.
It is an improved, more interactive version of a similar tool called `top`.

It's especially useful for when you're using shared computing resources, and want to make sure you're not going to crash the system or slow it down for other users.
If you start *multiprocessing*, it will also let you check that the computer is doing what you expect.

## Job control
By default, processes run in the "foreground"—they stop you from being able to interact with the terminal.
If you have a long running process, you might want to but it into the "background" so you can go back to using the terminal.
A background, or "non-interactive" job can't communicate with the user.

### Starting jobs in the background
Placing `&` at the end of a command starts its processes in the background.

### Moving jobs to the background
Jobs running in the foreground can be suspended by pressing `Ctrl+Z`.
This frees the terminal to run commands, but stops the job running.
It will give the job an ID, in case you're working with several suspended processes.

Suspended jobs can then be restarted in the background using the `bg` command.
By default it will move the "current" job, but you can pass the ID using a `%` symbol (e.g. `bg %2`).
Background jobs can be brought to the foreground using the `fg` command.

## `tmux` and `screen`
These are window managers or "terminal multiplexers".
They are used to split the single terminal into multiple virtual terminals.
This lets you run jobs interactively while still having free terminals that you can interactive.
You can also *detach* from virtual terminals, leaving their processes running in the background—like `bg`.

`tmux` is more modern and increasingly widely used, if you're picking one, give this a try.
However, only `screen` might be available on some computers.

## Sources
- [Baeldung Linux: Foreground and background processes](https://www.baeldung.com/linux/foreground-background-process.)
- [William Smith, The Linux Command Line](https://linuxcommand.org/tlcl.php)

< [The Command Line](./1_1_TheCommandLine.md) | [The File System](./1_3_FileSystem.md) >
