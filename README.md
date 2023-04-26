# Installing flask on an AWS EC2 instance

## Background

[Flask](https://flask.palletsprojects.com/en/2.3.x/) is a minimalistic Python library for creating web server applications.
For this assignment all we have to do is install flask and run the program here.

This guide roughly follows the [basic Flask install steps](https://flask.palletsprojects.com/en/2.3.x/installation/)

## Installation

### Installing pip

[pip](https://pypi.org/project/pip/) is a Python package manager - it is the recommeneded tool for installing Python packages.
We will install pip and use it to install the flask library/package.

#### Confirm you have python3
Run `which python3` and `python3 --version` to confirm Python 3 is installed.

**Note: Python 2 may be installed as `python` -- `python --version` may show python version 2. If this is the case be sure to use the `python3` command.
Many linux systems are set up this way for backwards compatibility with Python 2 programs. Using python 2 is not recommended.**

Now run `which pip` to confirm that pip is **not** installed.

For the following steps we will use the `apt` package manager. If you are on a Linux system and `apt` is not installed but `yum` is, use `yum`. 

```
sudo apt update
sudo apt install pip
```

Now type `pip --version` to confirm `pip` was successfully installed. 


### Create & activate Python virtual environment
A python virtual environment is a fancy term for a directory holding the python packages and correct version of the python language that our project uses.

We will learn more about this later, for today we will just follow these steps to get our flask server running.

Run the following commands where you want your flask webserver to live. Replace `myproject` with the desired name of your project directory. 
```
mkdir myproject
cd myproject
python3 -m venv .venv
source .venv/bin/activate
```

Your python virtual environment is now created and activated. Now, anything you install with pip is installed within this virtual environment.
You are not using multiple python virtual environments so don't have to worry about de-activating your environment; it is very lightweight and will not affect anything.

If you are curious, running `deactivate` will deactivate the virtual environment and `source .venv/bin/activate` will re-activate it again.

### Installing flask

With the virtual environment activated run `pip install flask` to install flask. If there is a `requirements.txt` file you could also run
`pip -r requirements.txt` to install all the python dependencies (such as flask) in the `requirements.txt` file.

