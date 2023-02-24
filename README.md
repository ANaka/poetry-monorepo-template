# poetry-monorepo-template

A template with some preferences for a poetry monorepo.

## Installation


### Set up `poetry` and `pyenv`

- Pyenv setup instructions: [https://github.com/pyenv/pyenv#installation](https://github.com/pyenv/pyenv#installation)
- Poetry setup instructions: [https://python-poetry.org/docs/#installation](https://python-poetry.org/docs/#installation)

#### Install Pyenv (macOS and Linux):

```bash
curl https://pyenv.run | bash
```

Follow the instructions to add the following to the end of your shell configuration (`~/.zshrc` or `~/.bashrc`):

```bash
export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
```

Restart your terminal.

Install Python 3.10 and set as local default:

```bash
pyenv install 3.10
pyenv local 3.10
```

#### Install Poetry (macOS and Linux)

```
curl -sSL https://install.python-poetry.org | python -
```

Follow the instructions to add `.local/bin` to your path, or just add the following to the end of your shell configuration (`~/.zshrc` or `~/.bashrc`) (make sure to add the full path to your home directory):

```bash
export PATH="$HOME/.local/bin:$PATH"
```

Restart terminal or run

```bash
source ~/.bashrc
# or source ~/.zshrc depending on your shell
```

Check poetry version - should show 1.2.0 or higher

```bash
poetry --version
```

### Clone repo

```bash
# Clone monorepo to your machine
git clone <repo-url>

# Change into monorepo directory
cd <repo-name>

# Install base package (just for pre-commit hooks)
poetry install

# Install pre-commit hooks
poetry run pre-commit install

```


### Git LFS

[Git LFS](https://git-lfs.github.com/) to store large files in the repo. To install Git LFS, follow the instructions for your OS:

```bash

# linux:
curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash
sudo apt-get install git-lfs

# homebrew:
brew install git-lfs

# initialize git lfs
git lfs install
```

`.gitattributes` file should take care of the rest.

### Installing a subpackage

```bash
# Change into package directory
cd projects/test_project # for example

# Set python version
poetry env use 3.11  # for example

# Create virtual env and install dependencies
poetry install # automatically does editable install of current package

# Inspect installed packages and see destination of virtualenv
poetry show -v
```

### Running scripts in poetry

Two options:

- use [poetry run](https://python-poetry.org/docs/cli/#run) e.g. `poetry run python <script.py>`
- use [poetry shell](https://python-poetry.org/docs/cli/#shell) to enter virtualenv and run scripts from there

### running jupyter kernels in VSCode

Update your VSCode setting `python.venvPath` to include your poetry virtualenvs path e.g. `~/.cache/pypoetry/virtualenvs`. You can find this path by running `poetry env info` in your terminal.
