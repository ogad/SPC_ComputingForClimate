< [Git](./4_1_Git.md) | [Python Environments](./5_1_PythonEnvironments.md) >

# GitHub
A place to put your repositories.

## Remotes
To collaborate or just to back up your work, you need to put your repository elsewhere.
We call copies of your repository which can push and pull changes to each other *remotes*.

The [`git remote`](https://tldr.inbrowser.app/pages/common/git-remote) command is used to show remotes.
`git clone` adds the original server as a remote called "origin", which your repo will be set up to track.
You can add remotes using `git remote add`, but unless you're working on a big collaboration or complicated repo, you'll be okay just with origin.

[`git pull`](https://tldr.inbrowser.app/pages/common/git-pull) collects data from the remote you're tracking, and then merges new commits into your repo.

When you have changes to add, you can use [`git push`](https://tldr.inbrowser.app/pages/common/git-push), specifying the remote you want to push to and the branch you want to push to it.
Most simply, you might run:
```bash
git push origin master
```
This only works if you've merged the most recent changes in the remote (origin) into your main branch (here called master).

## GitHub
GitHub is a place to store your repositories.
It is free (with pretty generous limitations), and your student status gives you access to pro features.
You can share repositories from here, and collaborate with others.

A good workflow to get into if you can is to make repositories on GitHub before cloning them to your local computer.
This keeps the structure consistent.

GitHub Pro (including student) includes access to CoPilot.
This is an AI model designed for coding, and is particularly good at code completions.
Logging into VS Code with your GitHub account, and making sure the CoPilot extension is installed, is all you need to do to get access.

## Sources
[Pro Git](https://git-scm.com/book/en/v2).

< [Git](./4_1_Git.md) | [Python Environments](./5_1_PythonEnvironments.md) >
