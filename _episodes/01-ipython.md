---
title: "IPython"
teaching: 15
exercises: 15
questions:
- "How can I use IPython for developing programs"
objectives:
- "Explain what IPython is for."
- "Demonstrate key features of IPython."
keypoints:
- "IPython provides an interactive environment for developing Python programs"
---

IPython is an interactive shell for the Python programming language that offers
enhanced introspection, additional shell syntax, tab completion and rich
history.

To start IPython, type the `ipython` command in a terminal window.

~~~
$ ipython
Python 3.5.2 |Anaconda custom (x86_64)| (default, Jul  2 2016, 17:52:12) 
Type "copyright", "credits" or "license" for more information.

IPython 4.2.0 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.

In [1]: 
~~~
{: .bash}

> ## Exiting IPython
>
> To exit IPython and return to the shell, type `exit` whenever
> a prompt is visible. You'll need to do this in order to
> edit a Python script with a text editor.
>
> ~~~
> In [1]: exit
> $
> ~~~
> {: .bash}
{: .callout}

IPython can be used to write Python programs interactively, however the more usual
workflow is to use a text editor to edit your code, save the file, and load and run it 
in IPython. You do this with the `%run` command. Let's start by creating a simple
Python program:

~~~
$ nano simple.py 
$ cat simple.py
def fib(n):
   if n <= 1:
       return n
   else:
       return(fib(n-1) + fib(n-2))
    
if __name__ == "__main__":
   for i in range(10):
       print(fib(i))
~~~
{: .bash}

Now it can be run in IPython using `%run`:

~~~
$ ipython 
Python 3.5.2 |Anaconda custom (x86_64)| (default, Jul  2 2016, 17:52:12) 
Type "copyright", "credits" or "license" for more information.

IPython 4.2.0 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.

In [1]: %run simple.py
0
1
1
2
3
5
8
13
21
34

In [2]: exit
$
~~~
{: .bash}

It is also possible to pass variables defined in the IPython environment to
the program using the `%run -i` command. If we change the code to:

~~~
$ nano simple.py 
$ cat simple.py
def fib(n):
   if n <= 1:
       return n
   else:
       return(fib(n-1) + fib(n-2))
    
if __name__ == "__main__":
   for i in range(num_values): # get num_values from IPython
       print(fib(i))
~~~
{: .bash}

The we can set the `num_values` variable with IPython:

$ ipython 
Python 3.5.2 |Anaconda custom (x86_64)| (default, Jul  2 2016, 17:52:12) 
Type "copyright", "credits" or "license" for more information.

IPython 4.2.0 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.

In [1]: num_values=5

In [2]: %run -i simple.py
0
1
1
2
3

In [3]: exit
$ 
~~~
{: .bash}

> ## Tab Completion
>
> Tab completion, especially for attributes, is a convenient way to explore the
> structure of any object you’re dealing with.
>
> To use completion, type a pattern you would like the shell to match,
> followed by the `Tab` key. 
>
> For example, to view an object's attributes, type `object_name.` followed
> by the `Tab` key.
> 
> Besides Python objects and keywords, tab completion also works on file and
> directory names.
{: .callout}

IPython distinguishes commands from Python objects using the `%` symbol. So
`%run` means run the Python program supplied as an argument. IPython calls
these _magic_ commands and provides many different commands. To see a list of
the available commands, use `%lsmagic`.

> ## %automagic
>
> By default, IPython will assume a command is a magic command unless there is a
> corresponding Python object with the same name. This means that it is possible to 
> enter magic commands without the `%` most of the time. The `%automagic` option toggles between this
> behavior and requiring a `%` to be present if the command is a magic command.
{: .callout}


