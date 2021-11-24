# Exploration of Gaussian processes for emulation of stochastic models

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/alan-turing-institute/stochastic-gp/HEAD)

This repository contains examples using Gaussian Processes (GPs) to emulate agent-based models.
Most of the files here use an agent-based model of bus movement as an example: the buses move between stops on a given route, picking up and dropping off passengers along the way.

The bus model simulation files are taken from the `BusSim` project, which is in turn part of the Data Assimilation for Agent-Based Models (DUST) project at the University of Leeds.
The [original `BusSim` code](https://github.com/Urban-Analytics/dust/tree/main/Projects/ABM_DA/bussim) is available from the [DUST repository](https://github.com/Urban-Analytics/dust) under an MIT licence; the relevant files are also included here.

## Setup

For a quick look around the contents of the repository, click on the Binder badge link above.
This will spin up a live instance of this repository in the cloud, with all packages installed for you.
Changes made to the code there can be downloaded as separate files, but you cannot edit this repository directly from Binder - rather, it is a good option if you simply want to explore the notebooks.

For further development, create a [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) of this repository, clone it and you will be able to edit and run the notebooks on your own computer.

Before running the code, you will need to install some Python packages.
Generally, it is recommended to set up a new project in a virtual environment.
To do so, run the following from the command line:
```
cd stochastic-gp
python3 -m venv venv
source venv/bin/activate
```

We will then use `pip` to install the required packages:
```
pip install --upgrade pip
pip install -r requirements.txt
pip install -r requirements-dev.txt
```

The `requirements.txt` file lists the packages needed to run the contents of the notebooks, while the `requirements-dev.txt` file lists utilities needed to use the project.
In this case, the contents of `requirements-dev.txt` relate to the Jupyter Lab installation.

To open Jupyter lab and explore the notebooks, run
```
jupyter lab
```

:question:
_Why is Jupyter Lab not included in the requirements.txt file?
This approach was taken to make it easy to set up Binder.
Binder detects a project's dependencies by searching for specific configuration files (here, `requirements.txt` and `apt.txt`).
Binder then builds a Docker image that contains all the project's required languages and dependencies.
As Binder itself provides the Jupyter Lab interface via Jupyter Hub, we do not need to install Jupyter Lab by default.
You can find out more about Binder [here](https://mybinder.readthedocs.io/en/latest/index.html)._

Note that some of the animated plots require a working installation of `ffmpeg`.
To install it, run
```
brew install ffmpeg        # on Mac, with Homebrew
sudo apt install ffmpeg    # on Linux, with apt
```
