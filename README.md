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
