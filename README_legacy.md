# Become a CADAn

The purpose of this guide is to provide high quality references to all the skills
required to be able to contribute towards CADA research projects, or data research
projects in general.

Most projects typically require collecting openly accessible datasets and analysing
them. Many projects also involve storing data in databases, transforming many different
datasets into a common format, visualising datasets, and publishing the results.

Python is good at all of these tasks, and has a shallower learning curve than many
other languages, so we are going to use it here.

## Installing python

Installing python can be a little tricky, especially on Windows (this might be a
common theme), so we have collected some useful resources here.

- [Windows](https://phoenixnap.com/kb/how-to-install-python-3-windows)
- [Mac OS](https://www.dataquest.io/blog/installing-python-on-mac/) often comes
with python 2 out of the box, but this is now incredibly out of date now, so we
want to make sure we are on python 3.
- Most linux distributions will have python3 as standard, but if you are on an
ubuntu-based system you can run `sudo apt install python`

## `pip`

`pip` allows us to install community written python packages.
These packages are uploaded to [the python package index (PyPI)](https://pypi.org/).
Anything on PyPI can be installed using a simple `pip install` command in the terminal.

## Editors

`python` is the application that converts our python code into something that
our computer can run.
You can write python code in loads of programs (even notepad if you fancy), but
using a good code editor will make your code writing experience a lot better.
It is entirely your choice, but some recommendations are:

- [VS Code](https://code.visualstudio.com/docs/python/python-tutorial)
- [Pycharm](https://www.jetbrains.com/pycharm/) - probably more suited to complete
python beginners.

## Virtual environments

Python is installed across our entire machine, but if we want to work on more than
one python project, then we want to isolate our python environments so that they
don't interfere with one another.
Therefore, we create a virtual environment for each project that we are working
on.
This will allow us to install packages in this environment only.

### `venv`

The most common way to create these environments is to use python's `venv` tool.

[Here is a deeper dive into `venv`](https://realpython.com/python-virtual-environments-a-primer/).

## git

Git is a version control program. It is also very good to enable effective collaboration
on a project. It is the standard way to manage a coding project.

There are many tutorials on git out there, [for example](https://www.freecodecamp.org/news/git-and-github-for-beginners/).

[Learn git with me](https://www.gitme.live/) is also a great interactive learning tool.

For any further reading, the important concepts are:

- [cloning a repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
to your machine (we use [github](https://github.com) to host our code)
- committing new code
- pulling / pushing
- branching - a common standard which we have adopted is to use github issues
as a to-do list, and then create a branch to work on this 'issue' before merging
the new feature onto the 'main' branch using a pull request after a peer review.

## databases

Research projects will require you to save the data you find. For simplicity, this
can start off in files (e.g. CSVs), but as the size and complexity of your data
increases, you will want to store it in a database. This will allow you to run
queries against big datasets rather than reading the whole dataset, as well as
many other benefits.

There are many types of databases out there, and the best one will depend on your
usecase, but for tabular data, you will probably want to use a SQL database.

### SQL

SQL (structured query language) is the language that we can use to construct queries
against our database. [Here](https://www.sqltutorial.org/) is a good tutorial on
SQL.

### duckdb

[duckdb](https://duckdb.org/) is a simple database solution that runs on your own
machine that can point to data stored on your machine, or on the cloud. This makes
it easy to share data across collaborators without having to pay too much (cloud
storage is cheap, but running programs, such as a database on the cloud is expensive)
and is why we have used it to store data for a few CADA projects already.

[Here](https://motherduck.com/blog/duckdb-tutorial-for-beginners/) is a bit more
information about duckdb.
