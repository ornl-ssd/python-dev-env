---
title: "PyDev"
teaching: 30
exercises: 0
questions:
- "How can I used PyDev to develop Python applications"
- "What are the main features of PyDev that will help me develop Python programs"
objectives:
- "Learn how to install PyDev."
- "Learn how to create Python packages and modules."
- "Understand the basic features of Eclipse."
- "Be familiar with terminology."
- "Experiment with the software engineering features of Eclipse and PyDev."
keypoints:
---

PyDev is an Eclipse-based development environment for Python programs. It provides a commercial-quality
environment for working on any size Python development projects. The main features provided by PyDev include:

* Syntax highlighting
* Code formatting
* Code completion
* Code analysis
* Type hinting
* Refactoring
* Visual debugging
* Unittest integration
* Code coverage

In addition, because PyDev is built using Eclipse, it also has available many of the development tools that
are integrated with the Eclipse environment, such as C/C++, Git, and modeling tools.

### Configuring PyDev

After starting Eclipse and selecting a workspace where your files will be kept (the default one is fine), you are
now almost ready to create your first project. Before doing this, however, we have to set up PyDev so that it knows
about your Python installation. This is particularly important if you've installed a new version, such as Anaconda,
in a non-standard location.

To start, we're going to first switch to the PyDev *perspective*, which is an arrangement of views and windows that
are designed to assist Python development. To do this, go to the **Quick Access**  box in the top right corner, and 
type "pydev". Choose the PyDev perspective from the list.

If this is the first time you've used PyDev, then you may see a dialog pop up like the one below. Don't panic! 
This is just PyDev telling you that it needs to configure the Python environment. If you're using Anaconda, 
then you'll need to select the **Manual Config** button.

<img src="{{ site.github.url }}/fig/03-pydev-dialog.png" width="50%"/>

This will open the PyDev Python interpreter preference page as shown below. Now click on the **New** button.

<img src="{{ site.github.url }}/fig/03-pydev-prefs.png" width="50%"/>

You should now see another dialog asking you to select the interpreter. Enter a name
(anything can be used here, e.g. "anaconda"), then click the **Browse...** button. Navigate 
to the installation location for Anaconda (usually called `anaconda3` in your
home directory), then select the `python` program in the `bin` directory. The image below
shows the dialog after the `python` progam was selected. PyDev worked out that this was 
Python 3.5 and changed the path to correspond to this version.

<img src="{{ site.github.url }}/fig/03-pydev-interpreter.png" width="50%"/>

Once you've done this, click the **OK** button. If you chose the right program, you should now see a dialog asking if you
would like a list of folders to be added to the SYSTEM pythonpath. Just click **OK** here.

<img src="{{ site.github.url }}/fig/03-pydev-folders.png" width="50%"/>

Finally, you should click on **OK** to save the preference changes.

### Your First Project

*Now* you are ready to create your first PyDev project. Here is a screenshot of the main window after switching
to the PyDev perspective. This is for Mac OS X, but it should look similar on Windows and Linux.

<img src="{{ site.github.url }}/fig/03-pydev-main.png"/>

You can ignore most of the icons and menus for now. The first thing to notice is that it is divided into two
parts. On the left is the PyDev Package Explorer. This is where your projects, packages, and modules will be
visible. On the right is a big empty area that we will be using to edit Python code soon.

To create a new project, select **File** > **New** > **PyDev Project** to open the *new project wizard*. There are
many settings that you can change on this dialog, but for now, just give your project a name (e.g. "my_project"). 
You also probably want to set the **Grammar Version** setting to **3.0 - 3.5** since we'll be using Python 3.5 in
this tutorial.

<img src="{{ site.github.url }}/fig/03-pydev-new.png" width="50%"/>

When you're done, select the **Finish** button and you should see the project appear in the Package Explorer view.
Clicking on the small triangle to the left of the project will open it. Notice there are no source files yet, however
you will see a reference to the "anaconda" interpreter we configured earlier. Opening this will show configuration
information used by the interpreter.

<img src="{{ site.github.url }}/fig/03-pydev-first.png">

Before creating a Python source file (called a *module* in Python terminology), you first must create 
one or more *packages*. The modules you create will then reside in these packages. To create a package, 
make sure you have the project selected in the Packager Explorer view, then select **File** > **New** > **PyDev Package**. 
If the **Source Folder** field is empty, then you didn't have the project selected (in which case, you can just 
manually enter "/my_project"). Now enter a package name (e.g. "my_package") into the **Name** field and select **Finish**.

<img src="{{ site.github.url }}/fig/03-pydev-package.png">

You will now see the new package has been created in the Package Explorer. It is also automatically created
an `__init__.py` module for the package (see [Packages](https://docs.python.org/3/tutorial/modules.html#packages) 
for more details.) Packages can also be nested within other packages. You can do this by selecting the destination package first in the
Package Explorer, then use **File** > **New** > **PyDev Package** to create the package.

>## Python packages
>
> Packages provide an important way of structuring Python's module (file) namespace, and are how virtually all
> Python libraries are distributed. It is good practice to always structure your Python code using packages. That
> way, even small programs can be easily distributed and reused.
{: .callout}

Modules must be created within a package, so select a package in the Package Explorer from the ones you have created,
the use **File** > **New** > **PyDev Module**. Give the module a name (without the trailing `.py`) and click on **Finish**.

<img src="{{ site.github.url }}/fig/03-pydev-module.png">

PyDev will now give you the opportunity to select from a predefined set of module templates. These templates provide an
easy way to create a module based on boilerplate code. You can also add your own templates if you desire.

<img src="{{ site.github.url }}/fig/03-pydev-template.png">

You can either select one of the templates from the list, or just hit **OK** and a new editor window will open on the module.

### Editor Features

If you used the `Module: Main` template, which adds a Python main program to the file, you will see something like
the image below. You can also see that the `pass` statement has been highlighted and this is where the cursor is 
located. When you begin typing, it will replace the `pass` statement with your code.

<img src="{{ site.github.url }}/fig/03-pydev-editor.png">

Notice there is syntax highlighting (color coding of keywords and strings), and also the there is an asterisk (`*`) next to 
the name of the module in the editor tab. This indicates that the file has been modified and needs to be saved. On the
right hand edge of the editor, there is a outline view of the code. The blue box represents the total extent of the code. 
Python statments, syntax errors, and the current insertion point are all shown pictorially in the outline view. At the bottom
of the editor are three status fields. The first shows permissions for the file being edited (`Writable`, `Read Only`, etc.).
The second shows the edit mode (`Insert` or `Overwrite`) which can be changed by double clicking on the field. The last field
shows the line and character position of the insertion point.

See the [PyDev Manual](http://www.pydev.org/manual.html) for complete details on how to use the editor.

### Running My Program

### Fixing Bugs

### Other Tools

 
