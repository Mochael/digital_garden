---
title: How to Use Pyenv
tree_state: 🌱
---

# What are the General Commands
- pyenv is a fantastic python package manager

`pyenv versions` to list out the various versions of python that have been installed on your computer.

Use  `pyenv versions` to check which versions of python you have installed and then
- The \* indicates which version of python is currently active for you

To install a new version of python with pyenv `pyenv install -v <version>`

If you want to switch your global python version run `pyenv global <version>`
- `pyenv global system` will set your default version of Python to your system's original version

To set the python version of a certain directory use `pyenv local <version>` while within the directory.
- This command creates a .python-version file in your current directory. If you have pyenv active in your environment, this file will automatically activate this version for you.

# How to set up a Virtual Environment
1. To create a new python virtual environment go into the directory you want the virtual environment and run the command `pyenv virtualenv <python_version> <environment_name>`
2. Now running `pyenv local <environment_name>` creates a .python-version file in your current working directory so that when you navigate to this directory you will automatically be inside this virtual environment

Now this directory will have it's own unique python packages and information, so when you navigate out of this directory, your python will automatically switch back to your global version.

# How to delete a virtual environment
1. Navigate to the .pyenv folder in your root directory (you can see it if you use `ls -a`) and then go into versions
2. Then `rm -rf <environment_name>` for the environment you want to delete