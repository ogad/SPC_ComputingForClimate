< [SSH and SCP](./3_2_SSH.md) | [Git](./Git.md) >

# SSH and SCP
Securely connecting your terminal to a remote machine.

## Connecting with `ssh`
[`ssh`](https://tldr.inbrowser.app/pages/common/ssh) is the program you can use to connect to a remote machine.

The command to connect to the remote machine is
```bash
ssh username@remote_host
```
This will prompt you to enter your password.

You will than login to the host, and start a shell session in your home directory.
Your shell configuration will be taken from the filesystem on the remote machine.
You can interact with the shell in the usual way, and (if you install the necessary software - e.g. XQuartz on your mac) you can use graphical elements via X11 forawrding.

## Transferring files with `scp`
[`scp`](https://tldr.inbrowser.app/pages/common/scp) is a command to copy files to and from a remote machine using ssh.

## Making it easier with ssh keys
`ssh` authenticates that the user and the server are who they say they are.
On the first connection, the server shares the key with the connecting user, and it is then stored as a "known host".

By default, the user is asked for a password each time a connection is made.
Some servers allow you to use an encrypted key to prove your identity, avoiding the need for you to type a password.
You generate a public/private key pair, and copy it to a server.
- Use [`ssh-keygen`](https://tldr.inbrowser.app/pages/common/ssh-keygen) to generate a key.
- Use [`ssh-copy-id`](https://tldr.inbrowser.app/pages/common/ssh-copy-id) to copy it to the server.

The keys are also important for syncing remote repositories (e.g. on GitHub) over ssh.
