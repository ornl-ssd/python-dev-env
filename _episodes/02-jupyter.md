---
title: "Jupyter Notebooks"
teaching: 15
exercises: 15
questions:
- "How do I use Jupyter Notebooks to write Python programs"
objectives:
- "Understand the architecture of Jupyter."
- "Be familiar with Jupyter terminology."
- "Experiment with running Python programs using Jupyter."
- "Understand the different output formats."
keypoints:
- "Jupyter provides a rich environment for developing Python."
- "Notebooks containing programs and output can be shared."
---

*Notebook documents* (or “notebooks”) are documents produced by the *Jupyter notebook app*, which contain both
computer code (e.g. Python) and rich text elements (paragraph, equations, figures, links, etc...). Notebook 
documents are both human-readable documents containing the analysis description and the results (figures, tables, etc..) 
as well as executable documents which can be run to perform data analysis.

The Jupyter notebook app is a server-client application that allows editing and running notebook documents 
via a web browser. The Jupyter Notebook App can be executed on a local desktop requiring no internet access 
or can be installed on a remote server and accessed through the internet.

When it is first started, the Jupyter notebook app displays a *notebook dashboard*. The dashboard allows the
user to open notebook documents, to view the status of running kernels, and start and stop kernels.

A *notebook kernel* is a “computational engine” that executes the code contained in a notebook document. 
The IPython kernel executes python code, but kernels are available for many other languages.

When you open a notebook document, the associated kernel is automatically launched. When the notebook is 
executed (either cell-by-cell or with menu **Cell** -> **Run All**), the kernel performs the computation and 
produces the results.

The Jupyter notebook app can be launched by typing in a terminal (cmd on Windows):

~~~
jupyter notebook
~~~
{: .bash}

This will launch a new browser window (or a new tab) showing the notebook dashboard. When started, 
the Jupyter notebook app can only access files in the current directory (or any sub-directories) when
it was launched. If you store the notebook documents in a different directory, you need will need
to change to that directory (or a parent directory) before launching the app.

Closing the browser (or the tab) displaying the dashboard or a notebook will not stop the Jupyter notebook app. 
TTo completely shut it down you need to terminate the `jupyter notebook` command you used to start the server.
Since closing the browser will not shut down the server, you can reopen a browser window and point it at 
`http://localhost:8888` to redisplay the dashboard.

When a notebook is opened, its kernel is automatically started. Closing the notebook browser tab, will not shut 
down the kernel, instead the kernel will keep running until is explicitly shut down. To shut down a kernel, go 
to the associated notebook and click on menu **File** -> **Close and Halt**. Alternatively, the dashboard 
has a tab named **Running** that shows all the running notebooks (i.e. kernels) and allows shutting them 
down (by clicking on a Shutdown button).

