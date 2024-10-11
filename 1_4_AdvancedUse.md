< [The File System](./1_3_FileSystem.md) | [Visusal Studio Code](./2_1_VisualStudioCode.md) >

# 1.4 More advanced use of the command line
## Expansions and escape characters
### Simple expansions
The shell "expands" your commands before it runs them.
Parts of your command get replaced, for example:
 - `*`, by a list of the files and directories in a path that match the "pattern"
 - `~`, by the path of the home directory.

### Arithmetic expansions
You can also expand arithmetic operations, which allow use of `+`, `-`, `*`, `/`, `%` and `**`.
They take the form:
```bash
$((expression))
```
For example $((2+2)).

### Brace expansion
**Brace expansion** creates multiple test strings from lists or ranges.
It's best understood by example:
```
~ $ echo Front-{A,B,C}-Back
Front-A-Back Front-B-Back Front-C-Back

~ echo Number_{1..5}
Number_1 Number_2 Number_3 Number_4 Number_5

~ $ echo {001..15}
001 002 003 004 005 006 007 008 009 010 011 012 013 014 015
```
(Recall that the `echo` command just shows the expression).

### Parameter expansion
Parameters, including *environment variables* can be expanded with a `$`.
For example `echo $USER`.

Environment variables are set up by the configuration and

### Command substitution
Commands inside commands can be expanded via`$(command)`.
For example, `echo $(ls)`.

### Controlling expansions
Double quotes can be used to prevent pathname expansion and barace expansion.
Quotes also prevent "word splitting"—where whitespace indicated separate arguments.
Sometimes you even need quotes to avoid the output of expansions being word-split (try `echo $(cal)` and `echo "$(cal)"`).

You can use single quotes to supress all expansions.

You can use backslashes to escape special characters (e.g. `\$`).

## Signals
Processes can be sent signals.
These tell the process to do something, for example Ctrl+C sends an `INT` signal, "interrupting" a running process.

This is also how Ctrl+Z works for foregrounding/backgrounding a process (sending the `TSTP`, terminal stop signal).

`kill` is a command to send signals to processes (and most importantly to kill processes that are otherwise out of control).
`htop` also has the capacity to kill and send other signals to processes.

## `sudo` and the root user
Some things need special privileges, like installing and updating software.
The `sudo` command does things as a superuser—as long as you have the right to do that on your machine.
You typically don't have the right to do it on shared machines (for security) and the admin will probably get an email if you try anything!

## Customisation
Customisation typically goes in the config files (`~/.bashrc` most of the time).
You can and should play around here—use `alias` to make shortcuts to commands, and configure the prompt as you like.


< [The File System](./1_3_FileSystem.md) | [Visusal Studio Code](./2_1_VisualStudioCode.md) >
