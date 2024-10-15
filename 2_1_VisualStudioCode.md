< [Advanced command line use](./1_4_AdvancedUse.md) | [Remote machines](./3_1_RemoteMachines.md) >

# Visual studio code
An editor with lots of extensions (and probably the main way I use my computer).

## Introduction
Code can be written in something as simple as notepad (or a command line text editor).
But it is nice to use something with more features, that has a graphical interface.
The extreme of this is an "Integrated Development Environment" (IDE) which has lots of specific tools for writing code (normally for a specific language).
A commonly used python IDE is "pycharm".

IDEs are often **paid-for software** (although pycharm is free for students).
They also don't always have a huge user base (so there isn't much support outside the company that makes it).
It is also not well suited to using lots of different technologies.
Spyder is a free IDE, which was the best free option for dedicated python development up to a few years ago.

A *code editor* is a newer type of tool which is increasingly popular for general-purpose computing.
Visual studio code (VS Code) is the most popular of these, developed by Microsoft but made open-source on GitHub.
Code editors are often free and open source, and successful code editors have huge user bases, with lots of extensions (providing many of the features an IDE would).
Zed is a newer code editor which is "one to watch" for the future.

## Workspaces and the window layout
VS Code can be used to just open files, make changes, and save them, but is most useful when used to **open folders**, creating a workspace.
The *primary side bar* can then be used in *explorer view* to view the folder's contents, or *search view* to search the contents of all the files in a workspace.
Files can be opened or created in the explorer view, and then edited in the main area, where *editors* can be opened.
Editors can be opened in tabs or arranged side-by-side.

The **panel** lives below the editor.
This provides access to a *terminal*, which has the workspace folder open as the working directory by default.
Errors and warnings are shown here too, in the *problems* tab.
Logs from processes managed by VS code are found in the *output* tab.
![The VS code interface](img/vscode_basicui.png)

The final important part of the interface is the **command palette**.
Cmd+Shift+P (Mac) or Ctrl+Shift+P (Windows) opens the command pallete, providing access to "actions" that the editor (or the extensions) can do, including quick access to preferences and file creation.
As a rough idea, the command palette gives access to anything you might be able to do with a keyboard shortcut (including actual shortcuts that you don't remember).
Another mode is "quick open" mode—opened using Cmd+P or Ctrl+P—you can quickly find files or *symbols* in your workspace.
**Symbols** are user-defined pieces of code—like variable or function names—the symbols in each file are shown in the *outline* under the Explorer view.

## Editing tips and tricks
### Multi-cursors
Using VS code, you can type in multiple places at once.
Holding option (mac) or alt (windows), clicking in an editor will place a new cursor, and typing will insert text at all the locations.
Alternatively, pressing Ctrl+D will highlight the current word, and repeatedly pressing it will add a new cursor highlighting successive occurrences.
This is super useful for e.g. changing a variable in a few places without using "Find+Replace" to change all occurrences.

Keyboard shortcuts can be used to place cursors in the sam eplace on the line above or below.
Cmd+option+up and Cmd+option+down will place a cursor on the line above or below (ctrl+alt+up/ctrl+alt+down on windows).

Each cursor has its own "copy/paste buffer" meaning that you can copy and paste from different lines, and each individual cursor will remember what it copied separately (useful if you're moving things around on multiple similar lines).

Finally, you can use "box selection" by holding option+shift (alt+shift on windows) and click-and-dragging.

### Line actions
Line actions edit the whole line where the cursor is (or all the lines selected).
- Option+up/Option+down (alt+up/alt+down on windows) moves a line up or down.
- Option+shift+up/Option+shift+down (alt+shift+up/alt+shift+down on windows) makes a copy of a line futher up or down.
- Cmd+/ (Ctrl+/ on windows) comments out a line.
- Cmd+Shift+K (Ctrl+shift+K on windows) deletes lines.

### Intellisense
This is a suggestions widget that will pop up with functions and variables as you code.
You can trigger it with Ctrl+Space.

### Renaming and refactoring
You can rename a function or variable and automatically update all the files that refer to it by using the "rename" functionality.
Trigger the rename window by pressing F2 when your cursor is in a *symbol* anywhere in your code, you can also right click and select "Rename symbol".

Right clicking and selecting "refactor" brings up suggestions to structural changes you could make.
This is useful when you want to move whole definitions to new files, or generate documentation.

## Extensions
Extensions provide a lot of functionality to VS Code.
They are used to provide language specific suggestions, formatting, debugging, compilation, etc.
The *Extensions view* in the primary sidebar is used to find and install extensions and "Extension packs".

All the python-specific functionality comes from extensions (mostly developed at Microsoft by the VS Code Team).
The core extensions for supporting python development are found in Microsoft's **Python extension pack** including:
- **Pylance**: Basic language support (autocomplete, IntelliSense, and code linting).
- **Python debugger**: An interactive debugger for python.
Other important extensions are:
- **Jupyter** Supports Jupyter notebooks and IPython.
- A formatter, such as **Black** or **autopep8**
- A linter, such as **pylint**.
- **isort** for sorting imports.

Other extensions extend VS Code in many different ways.
Some extensions I use include:
- The **Remote Development Pack** for development using remote workspaces.
- **TODO Highlight** to highlight note-to-self "TODO" comments.
- **GitHub Copilot** for AI code development help.
- **GitLens** for lots of source control features.
- **indent-rainbow** to make indentation clearer.
- **LaTeX Workshop** and **LaTeX Utilities** for editing LaTeX documents without overleaf.
- **Project Manager** for keeping a list of workspaces to hand.


## Sources
- [Jetbrains: IDEs vs. Code Editors](https://blog.jetbrains.com/webstorm/2024/03/ides-vs-code-editors/)
- [Visual Studio Code Documentation](https://code.visualstudio.com/docs/), specifically:
  - [Tutorial](https://code.visualstudio.com/docs/getstarted/getting-started)
  - [Tips and Tricks](https://code.visualstudio.com/docs/getstarted/tips-and-tricks)
  - [User interface](https://code.visualstudio.com/docs/getstarted/userinterface)
  - [User guide](https://code.visualstudio.com/docs/editor/codebasics)
  - And [Python](https://code.visualstudio.com/docs/python/python-tutorial)


< [Advanced command line use](./1_4_AdvancedUse.md) | [Remote machines](./3_1_RemoteMachines.md) >
