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

- **Key Point**: `if __name__ == "__main__"` only runs when the program is called directly, which means that if you import a file and wanted to test the functions independently via the intrepretor you can without running the entirety of the program. So when you call the script as a standalone, directly, it can run specific code, but when called as a module, it can expose functions without automatically running the code for direct execution

### Understanding Python Packages

**Packages** in Python help you organize and structure your code using "dotted module names." This allows you to manage complex projects with multiple modules more easily. For example, if you have a package named `A` and inside it a submodule named `B`, you can access the submodule with the name `A.B`.

Just like using different variables in separate modules helps avoid name conflicts, **packages** with dotted names help different projects (like NumPy or Pillow) avoid conflicting module names.

### Example: A Sound Package

Imagine you're creating a package to handle different sound files and sound data. There are many sound formats like `.wav`, `.aiff`, or `.au`, so you'll need to make a set of modules to convert between these formats. You might also want to create modules for sound effects (like adding echo or applying an equalizer).


### How Python Finds Packages

When you **import** the package, Python looks through directories in `sys.path` (a list of directories) to find the package folder.

- The `__init__.py` files are important because they tell Python that the directory should be treated as a package. These files can be empty, or they can contain initialization code for the package.
- Without the `__init__.py` file, Python won't know it's a package and may accidentally mix up similar directory names.

## What is `__pycache__`?
- It is a directory of code that has been compiled before and basically if that code is called again it makes the program more efficient because the program knows the output
- before code is compiled it is stored in intermediate files called `bytecode` and it makes python faster to execute this file than recompile

## What is Pathlib?
- it represents file paths as objects, making it easier to perform common file system operations like creating, joining, and manipulating paths
- `pathlib.Path` represents file system paths as objects, making it easier to work with paths, abstracts the underlying OS, **and it provides methods to check if a file exists, reading/writing to files/ creating directories**

## Pytest

- Unit Test Utility that makes it wasy to run unit tests
- `-vv` will give you maximum verbose ouptut
- `-s` for stdout output
- `-x` stops at the first error
- `--last-failed` reruns last failed test
- `--pdb -s` automatically starts debugger when a failure occurs
- `--trace -s` starts a debugger on the first line of the test
- `-s` sets a breakpoint

## Shell Scripting

- Automates command line tasks
- Each line of code in a shell script is a command that could be entered at the command line
- make an extentionless file and write command line arguments in each line 
- you can use `#` for comment purposes
- run command `chmod +x {file_name}` to create executable and then `./{file_name}` to run executable
- all shell scripts need a special first line beginning with `#!/bin/bash` do not forget it
- By default, shells cripts do not stop on errors so you need to set the permission to do this `set -Eeuo pipefail` 
- `ls -l {file_name}` will tell you the permissions of the file

