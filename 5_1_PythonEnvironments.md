< [Remotes and GitHub](./4_2_GitHub.md) | [Using Python](./5_2_IPython.md) >

# Python Environments
A place to put your packages.

## Introduction
### Environemnts
Environments are separate python installations which can use different package and python versions.
When an environment is *activated*, the command line will use the software installed in that environment (the activation sets all the relevant environment variables, so the shell knows where to find different programs).

Environements are useful because python is easily confused—**dependencies** aren't managed well, so code that works with one installation may break when used with a different version.
Using a virtual environment avoids "polluting" the system installation, and lets you keep track of all the code that works with a specific project.
You can also export and reproduce the environment elsewhere to get your code working on a new machine more easily.

### Conda
Conda is a package and environment manager—it can be used to create and install packages.
Conda is also more versatile than python's built-in package manager (called `pip`) because it can be used to install non-python packages in an environment.

Conda makes an effort to check for **package dependencies**, meaning its environments break less often, but this means it can be slow to "resolve" package installations.
This is particularly true when using the default installation, because the "channel" which is used to find and download packages doesn't have all the packages you might need.
[Conda Forge](https://conda-forge.org/docs/user/introduction/) is a project to provide **all packages** you might want.
Using this channel makes conda lots faster (usable).
Conda forge can be added to an existing installation using the [instructions on the documentation](https://conda-forge.org/docs/user/introduction/#how-can-i-install-packages-from-conda-forge) or included in new installations by installing conda with [Miniforge](https://conda-forge.org/download/)

## Creating and activating environments with conda
By default you might have a "system installation" of python.

After installing conda, it will create a "base" conda environment.
It is reccommended that you don't install things directly here (it's a good idea to keep an environment you know is stable).

To create an environment use the [`conda create`](https://tldr.inbrowser.app/pages/common/conda-create) command.
You can specify packages (or python versions) to include when creating, or use [`conda install`](https://tldr.inbrowser.app/pages/common/conda-install) after creation.

## Sources
[Real Python—Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)

< [Remotes and GitHub](./4_2_GitHub.md) | [Using Python](./5_2_IPython.md) >
