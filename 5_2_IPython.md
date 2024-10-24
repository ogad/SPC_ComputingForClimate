< [Python Environments](./5_1_PythonEnvironments.md) | [Python for Scientific Computing](./5_3_PythonScientificComputing.md) >

# Using Python
The different options for writing and running code.

## The python interpreter
The [`python`](https://tldr.inbrowser.app/pages/common/python) command gives you access to the **Python interpreter**—it runs python code.
Run without argument, it provides an interactive shell (or REPL), or when given a file it executes it (runs it's content line-by-line).
We give python files the extension ".py".

## The IPython interpreter
[`IPython`](https://tldr.inbrowser.app/pages/common/ipython) is an enhanced version of the python interpreter and can also be used to run scripts or start a REPL.
It adds [access to the shell](https://jakevdp.github.io/PythonDataScienceHandbook/01.05-ipython-and-shell-commands.html#Shell-Commands-in-IPython), [enhancements called "magics"](https://jakevdp.github.io/PythonDataScienceHandbook/01.03-magic-commands.html), [input and output histories](https://jakevdp.github.io/PythonDataScienceHandbook/01.04-input-output-history.html), and [access to documentation and source code](https://jakevdp.github.io/PythonDataScienceHandbook/01.01-help-and-documentation.html).

## Jupyter notebooks
[Jupyter](https://docs.jupyter.org/en/latest/) is a project to encourage the use of **notebooks**.
These are ".ipynb" documents which contin runnable code as well as readable text, data, and visualisations/output.
This makes them great for sharing/explaining code.
Jupyter notebooks use a **kernel** running in the background—they use IPython to provide this kernel, which provides the interpreter specific to your environment.
Code (or text) is written in **cells**.
Code cells can then be passed to the interpreter one at a time, and they display their output inline.
Jupyter notebooks can be used via a "Jupyter notebook server"—started on your computer using the [`jupyter`](https://tldr.inbrowser.app/pages/common/jupyter) command, or provided by an HPC.
Alternatively, [VS Code supports opening Jupyter notebooks directly](https://code.visualstudio.com/docs/datascience/jupyter-notebooks#_create-or-open-a-jupyter-notebook).

## Jupyter code cells
A REPL is good for rapidly writing code and seeing what happens, but what you write is quickly lost if you close the window.
A notebook gives access to this development style (writing and rapidly running code) in documents you can save, edit and keep.
However, notebooks are bulky, complicated documents designed for sharability—they store a lot more metadata and outputs than a plaintext ".py" file, and therefore they don't work very well with Git (although Git and GitHub have some reasonable support, they still take up a lot of space).
**Code cells and the "Interactive window"** are provided by VS Code to solve this problem.

In a .py file, a comment beginning `# %%` marks a Jypyter-like code cell.
In VS Code, these cells can then be run in a notebook-like interface called the "interactive window" which will show code output.
You can also type code directly into the interactive window (useful to e.g. examine variables you've made or prototype before adding code to the file).
This is also running on top of an IPython kernel (you can choose the environment you'd like to use).
![Jupyter code cells running in the interactive window via VS Code.](./img/ipython_interactivewindow.png)

More information is in the [VS Code documentation](https://code.visualstudio.com/docs/python/jupyter-support-py).

## Sources
[Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/01.00-ipython-beyond-normal-python.html)
[Project Jupyter](https://docs.jupyter.org/en/latest/)
[VS Code — Working with Jupyter code cells](https://code.visualstudio.com/docs/python/jupyter-support-py)

< [Python Environments](./5_1_PythonEnvironments.md) | [Python for Scientific Computing](./5_3_PythonScientificComputing.md) >
