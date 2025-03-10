# Become a CADAn

The purpose of this guide is to provide high quality references to all the skills
required to be able to contribute towards CADA research projects, or data research
projects in general.

Most projects typically require collecting openly accessible datasets and analysing
them. Many projects also involve storing data in databases, transforming many different
datasets into a common format, visualising datasets, and publishing the results.

Python is good at all of these tasks, and has a shallower learning curve than many
other languages, so it is the recommended language for CADA projects.

If there is a topic that is missing from this document, then do [create an issue](https://github.com/cada-network/become-a-cadan/issues/new/choose)
detailing what you'd like to learn.

## Python basics

If you are a complete beginner, then it's probably worth doing an online course
as these help you get the hang of python without getting thrown straight into the
deep end. Some suggestions are:

- [codeacademy](https://www.codecademy.com/learn/learn-python-3)
- [datacamp](https://www.datacamp.com/courses/intro-to-python-for-data-science)
- [makersacademy](https://github.com/makersacademy/intro-to-python/blob/main/000_START_HERE.md)

## Running python

The easiest way to write and run python code as a beginner is using a service such as 
[google colab](https://colab.google/). This gives an environment where you can write / run
python code directly from your web browser. This essentially stores and runs your code
on google machines.

## Installing python

To work with python on your own machine, you need somewhere to write python code, and a way to run
python code.

### Editors

`python` is the application that converts our python code into something that
our computer can run.
You can write python code in loads of programs (even notepad if you fancy), but
using a good code editor will make your code writing experience a lot better.
It is entirely your choice, but our recommendation is:

- [VS Code](https://code.visualstudio.com/docs/python/python-tutorial)

Installing python used to be a little tricky (see the [legacy README](./README_legacy.md)),
but a tool called `uv` is simplifying a lot of python tooling, including installing
python itself, so it is recommended to install `uv`.

- [Here is a guide to installing `uv`](https://docs.astral.sh/uv/#getting-started).
- [Here is a deep dive into `uv`](https://www.saaspegasus.com/guides/uv-deep-dive/).

Run this command in your command line:

`uv python install`

## Python youtube channels

There is a lot of great content on youtube for learning python. Some great content
creators are:

- [freeCodeCamp](https://www.youtube.com/@freecodecamp) - all levels
  - [full beginner course](https://youtu.be/rfscVS0vtbw?si=BBVwGtS-AB0fMB9f)
  - [python basics](https://www.youtube.com/playlist?list=PLWKjhJtqVAbkmRvnFmOd4KhDdlK1oIq23)
  - [data analysis with python](https://www.youtube.com/playlist?list=PLWKjhJtqVAblvI1i46ScbKV2jH1gdL7VQ)
- [Corey Schafer](https://www.youtube.com/@coreyms) - all levels
  - [Python Programming Beginner Tutorials](https://www.youtube.com/watch?v=YYXdXT2l-Gg&list=PL-osiE80TeTskrapNbzXhwoFUiLCjGgY7)
- [NeuralNine](https://www.youtube.com/@NeuralNine) - intermediate / advanced
  - [Python Intermediate Tutorial](https://www.youtube.com/watch?v=2S7Xxz9PhaU&list=PL7yh-TELLS1F3KytMVZRFO-xIo_S2_Jg1)
- [ArjanCodes](https://www.youtube.com/@ArjanCodes) - intermediate / advanced
- [Carberra](https://www.youtube.com/@Carberra) - advanced

## Python projects

Any project that you do in python will want to be in its own folder on your machine.
I find it helpful to store these all in a folder called `code` folder in my home
directory, as this is always very accessible.

For each individual project, python uses a file called the `pyproject.toml` file
that contains all the information required for a project. This includes things
like the name / description of the project, the version(s) of python that it runs on, 
any third party dependencies, etc.

The `uv sync` command will sync your environment with the `pyproject.toml` file
(including downloading / installing dependencies).

More info can be found [here](https://www.youtube.com/watch?v=QMY-OkckDwo),
but I wouldn't look too much into it. It is mostly useful for keeping track of dependencies.

## Virtual environments

When we install python, it is installed across our entire machine. But when we want
to work on more than one python project, then it is important to isolate our python
environments so that they don't interfere with one another.
Therefore, we create what is called a 'virtual environment' for each project that we are working
on.
This will allow us to install packages in this environment only.

`uv` handles virtual environments very easily for each project.
When you are in a project folder, `uv sync` will get your virtual environment
synced with the `pyproject.toml` file, including creating a virtual environment.

[Read more here](https://pip.pypa.io/en/stable/reference/build-system/pyproject-toml/)

### Installing packages

The [python package index (PyPI)](https://pypi.org/) contains thousands of community-developed
python packages that can be installed and used in our projects.
To add one as a project dependency, run

`uv add <package name>`

This will install it to our virtual environment and add it to our list of project
dependencies in our pyproject.toml file, which will allow others working on the
project to install it as well when they run `uv sync`.


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

#### motherduck

[motherduck](https://motherduck.com/) provides an option to run `duckdb` on the
cloud at a reasonable cost. It is useful for our size of project where we don't
have 'huge' (100+ GB) amounts of data, but would benefit from sharing the database
rather than just the files.

### 'big' data

Each cloud platform has their own offering for databases bigger than this.
[Google bigquery](https://cloud.google.com/bigquery) is probably the best value
as other options such as [snowflake](https://www.snowflake.com/en/data-cloud/workloads/data-warehouse)
and [redshift](https://aws.amazon.com/redshift/) can get very expensive very quickly.

## Web scraping

Web scraping is a way to collect data from websites.
The [requests](https://realpython.com/python-requests/) library is how we download
data from websites and from REST APIs to use in python.

HTML websites can be parsed using [beautiful soup](https://www.scrapingbee.com/blog/python-web-scraping-beautiful-soup/).
A bit of understanding of HTML elements and CSS selectors will help use beautiful
soup.

Requests works well for static and basic websites, but for more complex pages,
or filling / submitting forms, use [selenium](https://www.geeksforgeeks.org/selenium-python-tutorial/).

[John Watson Rooney](https://www.youtube.com/@JohnWatsonRooney) has a brilliant
youtube channel for content on web scraping.

## dataframes

Dataframe libraries are useful for applying powerful transformations to datasets.

[pandas](https://pandas.pydata.org/docs/user_guide/10min.html) is the most commonly-used
dataframe library, but [polars](https://docs.pola.rs/user-guide/getting-started/)
is a modern library that is easier to use (especially for beginners) and faster.
Therefore, we would recommend using polars in CADA projects.

## Running code

To run a python script, run the following command `uv run <path to script>`.

Running `uv run python` in the command line takes you to the python ['REPL'](https://www.learnpython.dev/01-introduction/02-requirements/05-vs-code/04-the-repl-in-vscode/)
where you can run python code directly in the terminal.

Running [`uv run --with=ipython ipython`](https://ipython.org/) gives a more interactive shell.

[jupyter notebooks](https://www.datacamp.com/tutorial/tutorial-jupyter-notebook)
go a step further and give a full notebook environment to run code.
`uv run --with=jupyter jupyter-notebook`

## Visualising / plotting

There are many plotting libraries in python. Many are not great, but [plotly express](https://www.datacamp.com/tutorial/python-plotly-express-tutorial)
is a decent library that creates interactive charts with simple but powerful syntax.
