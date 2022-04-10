# NH Python Virtual Environments

Materials for a Virtual Environments lightning talk for NH Python meetup in April 2022.


## Outline

- What are virtual environments?
    - [venv documentation](https://docs.python.org/3/library/venv.html): "A virtual environment is a Python environment such that the Python interpreter, libraries and scripts installed into it are isolated from those installed in other virtual environments, and (by default) any libraries installed in a “system” Python, i.e., one which is installed as part of your operating system."
- Why should you use them?
    - If need different versions of same package for different projects
    - If working on managed servers or production environments where can't modify system-wide packages because they have specific package version requirements (Dataquest article)

### Python's `venv` module

- Part of standard library since Python 3.3
    - Built off of `virtualenv` PyPI package (needed to install via PIP) in Python 2
- Installs the virtual environment in your current working directory, so make sure to navigate there first
    - Will use the version of Python that you run to create the environment
- Pros: easy to use, don't need to install anything, works with PIP
- Cons: not 'globally' available for any new project
    - Unless you're willing to type the exact path to the virtual environment, can't realistically use it for other projects

```shell
# Create a project folder and navigate into it
mkdir my_proj
cd my_proj

# Create a virtual environment named "proj_venv"
python3 -m venv proj_venv

# Activate the new environment
source proj_venv/bin/activate

# Install packages
python -m pip install <package_1> <package_2==1.0.0> <'package_3>2.4'>

# Create a requirements.txt file with all packages/versions
pip freeze > requirements.txt

# Install packages into an environment from a requirements.txt file
python3 -m pip install -r requirements.txt

# Deactivate an environment (environment name is optional)
deactivate proj_venv
```

### Anaconda: Conda and Miniconda

