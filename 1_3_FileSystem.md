< [Processes](./1_2_Processes.md) | [Advanced command line use](./1_4_AdvancedUse.md) >

# 1.3 The file system
Learn how to find files and manage disk space effectively in your Linux file system.

## Finding files
Commands for finding files include:
- [`find`](https://tldr.inbrowser.app/pages/common/find) Search the file system for files.
- [`grep`](https://tldr.inbrowser.app/pages/common/find) Find files containing specific text, based on *regular expressions*.
- [`locate`](https://tldr.inbrowser.app/pages/common/pwd) Search a cached version of the file system (much faster than `find`, once the cache is generated).

## Permissions
Files and directories all have permissions, controlling who can read, write, and execute them.
Permissions, viewed in the output of `ls -l` are denoted by a string of 10 characters.
Missing permissions can often be the cause of issues, so they're worth checking.

An example permissions string is:
```-rwxr-xr--```
This is split into sections:
  - An initial `-` (file) or `d` to denote the type.
  - Three characters for the file owner's permissions (here `rwx`).
  - Three characters for the permissions of the group assigned to the file (here `r-x`).
  - Three characters for everyone else's permissions.

The characters of the permission strings denote **r**ead, **w**rite, and e**x**ecute permissions (the permission is denied if there is a `-` character).

Permissions can be changed with the `chmod` command (but this needs permissions—you might need to ask the file owner).

## Managing storage
Some commands are useful for checking disk usage and available space.
- [`du`](https://tldr.inbrowser.app/pages/common/du)
- [`df`](https://tldr.inbrowser.app/pages/common/df)

Options for "human readable" sizes can be useful—this is often `-h`.


< [Processes](./1_2_Processes.md) | [Advanced command line use](./1_4_AdvancedUse.md) >
