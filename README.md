# 485 Notes for Standard Coding Practices

This document will encompass concepts and useful things to know for industry best practices.

## What is a Virtual Environment and Why is it Used?

- A virtual environment allows you to download remote packages for a specific project.
- It is useful because some projects may have colliding packages, and certain versions of a package may not work for a particular use case. By using a virtual environment, you can isolate and download those packages for that specific project.
- **Example:** At Noblis, Python 3.12 did not support YOLOv8, and Python 3.12 was installed on the local machine. Therefore, I had to download a virtual environment to install Python 3.11.9 for YOLO to work for that specific project. This is one of the key benefits of virtual environments.
- To create and activate a virtual environment, use the command: `source env/bin/activate`. To deactivate, use the command: `deactivate`.
- If the project has starter files, activate the virtual environment and use the command: `pip install -r requirements.txt` if a `requirements.txt` file is included.

## What is an `__init__.py` File?

- All packages have this file.
- This file marks a directory as a Python package.
- The code within this file can be imported from other Python scripts.

## How to make `main` work

- Create a `def main:` function where the main command line stuff will be processed as well as the main functionality
- underneath you will have `if __name__ == "__main__"` where you call the `main` function

## What is `if __name__ == "__main__"`?

- It allows the Python program to be used as a standalone program as as a module that can be imported to other scripts
- When using as script a program sets its own variables and one of them is `__name__` and that is set to `__main__`
- the line `if __name__ == "__main__"` checks if the script is being run directly or being imported as a module

## Modules in Python

-if you create a file with a cetain name and make functions within them, you can then load up the python interpretor in the terminal and then say `import {file_name}` and then use `{file_name}.{function_name}` to access and test the functions within the file
- **Namespace** packages: have no physical attribution and acts as a container for subpackages, it also has no `__init__.py` file.

- If the module is run directly (i.e., as the main program), `__name__` will be set to `__main__`.

For example, if you run a script directly from the command line like `python file_name.py`, then within that script, `file_name.__name__` would be `__main__`.
If the module is imported into another script or an interactive session (like the Python interpreter), then `__name__` will be set to the name of the module (which is the file name without the .py extension).

For example, if you have a module called `my_module.py` and you import it in the interpreter like `import my_module`, then `my_module.__name__` will be `my_module`.

