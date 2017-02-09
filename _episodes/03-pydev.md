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
(anything can be used here, e.g. "anaconda"), then click the **Browse...**. Navigate to the installation location for
Anaconda, then select the `python` program in the `bin` directory. The image below
shows the dialog after the `python` progam was selected. PyDev worked out that this was 
Python 3.5 and changed the path to correspond to this version.

<img src="{{ site.github.url }}/fig/03-pydev-interpreter.png" width="50%"/>

Once you've done this, click the **OK** button. If you chose the right program, you should now see a dialog asking if you
would like a list of folders to be added to the SYSTEM pythonpath. Just click **OK** here.

<img src="{{ site.github.url }}/fig/03-pydev-folders.png" width="50%"/>

Finally, you should click on **OK** to save the preference changes.

### Your First Project


### Editor Features

### Running My Program

### Fixing Bugs

### Other Tools

 
