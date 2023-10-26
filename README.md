# GitHub Action written in Python

This is a Python template for GitHub actions, allowing using Python to inject Python modules
into GitHub Actions.

This template is designed for those with basic knowledge of Python 3.

> **Warning**: Python 3.x scripting support is not an Actions built-in.
> 
> Please be careful using this template, as GitHub does not offer support for this
> example. This project was designed to provide extended code support for GitHub
> Actions.

> **Note**: On Windows, the action will occur on WSL which means all commands in the
> workflows that depend on a Python action must run on WSL (therefore use Unix paths).
> But **why**? Because this action uses `bash` as the shell, which on Windows basically
> starts a WSL session, but on Linux, starts a Bash shell.

## How to use

Click [here](https://github.com/TylerMS887/python-gh-action/generate) to create a new
Python action. This opens the GitHub generation interface, which creates a new repository
containing the contents of this repository.

After creating your Python action, delete this README and create a new one to describe
your action, the options it can handle, and an example of using it.

Metadata is in the `action.yml` file, just like most other GitHub actions. Edit
`src/action.py` to change what your workflow does.

## How it works

This GitHub action works as a composite script. It:
1. Installs dependencies. Python support for GitHub Actions offers the Python package manager,
   `pip`. `requirements.txt` and `src/requirements.txt` will be installed if one of them exist.
3. Runs the code for the action from `${{github.action_path}}/src`.
