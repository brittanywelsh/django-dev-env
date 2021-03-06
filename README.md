# django-dev-env
## Quick development-environment setup for lazy people.

This is a simple bash script that runs a list of installation commands, to simplify setup of a new development VM. It is intended to be used on a fresh Ubuntu installation in a zsh shell, perfect for [Nitrous containers](http://www.nitrous.io)!

### Installation

From your development machine, first download `setup.sh`, and edit the script variables in that file. (You don't have to download the whole repo; the setup script will pull the cheat sheet and sourcefile using curl.)

```
curl -L https://raw.githubusercontent.com/brittanywelsh/django-dev-env/master/setup.sh > setup.sh
# [NOTE - at this point, edit the setup.sh variables to suit your needs!]
sudo chmod u+x setup.sh
./setup.sh
```

OR, if you're me, try this (but if you're not me, remember to re-configure your git settings back to your own name and email!):

```
curl -L https://raw.githubusercontent.com/brittanywelsh/django-dev-env/master/setup.sh | zsh
```

### What gets installed?

Here's the full summary of what the `setup.sh` script runs:

1. Update/upgrade Ubuntu packages (via apt-get)
2. Configure git
3. Install PostgreSQL and python-psycopg2 (via apt-get)
4. Install python-setuptools (via apt-get)
5. Install pip (via easy-install)
6. Install pyenv (via [pyenv-installer](https://github.com/yyuu/pyenv-installer))
7. Install Python via pyenv
8. Install virtualenv and virtualenvwrapper (via pip)
9. Install Ruby (via apt-get)
10. Install the Heroku toolbelt
11. Install a "cheat sheet" (see below for usage)
12. Add sources to ~/.zshrc file

All of the information printed out to the screen during the installation process is also nicely logged for you in a file located in your home directory, `~/.my_dev-env_setup.txt`, so later you can double-check what exactly the script did.

**NOTE:** pyenv, virtualenv, virtualenvwrapper, and cookiecutter are all installed globally, i.e. not contained within any kind of virtual environment. Make sure you understand the implications of this in your own environment!

### Using the Cheat Sheet

The setup script will create a new folder in your home directory called `~/.cheat/`. Inside this folder is a shell script, named "cheat", which you can invoke at any time by typing `cheat` into your shell. It contains some useful syntax/reminders. Feel free to edit your cheat file to add your own commands!

**NOTE:** to use `cheat` for the first time after running the installation script, you will have to open a new shell so that the path variable is updated appropriately.
