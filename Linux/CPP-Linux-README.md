# Setting up C++ Development Environment on Ubuntu Linux

## Tools

- Visual Studio Code
- git version control
- g++ compiler
- Jupyter Notebook
- C++ kernel for Notebook

## Instruction Notes

- **\$** is default prompt for regular user and is always there on a Bash Terminal
  - you don't type it as a part of command
- **#** on bash command is comment ignored by the Terminal
  - you don't need to type it as a part of command
- any command that starts with **sudo** keyword requires admin (sudo in Linux) priviledge and prompts for your password
- **\< ... \>** - is a place holder that must be completely replaced (including the angular brackets) with actual content in place

## Install Visual Studio Code

- recommended editor for writing C++ code, compiling and debugging
- editor that has many built-in features including git, terminal and many third party plugins to support many programming languages
- download and install the right version for your machine from here:
   [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

## Run Terminal

- any time you need to run bash commands, you must do it from a Terminal app
- follow these steps to run Terminal

1. search for Terminal
2. click to run Terminal App
4. Right click Terminal app on dock and pin it to favourites for quick access in the future

## Install command-line developer tools (g++, git, etc.)

1. make sure you're on a Terminal
2. run the following commands on the Terminal

```bash
x-code-select install #installs compiler and many other relevant command-line tools
g++ --version # check if g++ is installed
git --version # check if git is installed
```

## Configure Git to authenticate with ssh keys

- using ssh keys is not required but is recommended as it let's you authenticate with GitHub server or other git repo hosting sites (Gitlab, Bitbucket, etc.) so you don't have to type username/password all the time
  - and YES, you'll be have to authenticate quite frequently while pulling and pushing code from the server
    - ssh keys will make your life lot easier
- these steps you do once on each system you are using Git on

1. make sure you're on a Terminal
2. let git know who you are; use your real name and email you registered on GitHub
    - enter the following commands; double quotes are required

```bash
git config --global user.name "<your full name>"
git config --global user.email "<email you used for github.com>"
```

3. check if you've public/private key pair already genereted

```bash
ls ~/.ssh/  # list the contents of ~/.ssh/ folder
```

4. if you see id_rsa id_rsa.pub files, you have public/private key pairs, so you don't have to generate one
5. if no key pair exists, generate one
    - pick default location to save the key and just hit enter key for password (or do not use password!)

```bash
ssh-keygen
```

7. simply hit enter until you get the **\$** prompt back when generting keys
8. list the content of the public key file to copy to GitHub

```bash
cat ~/.ssh/id_rsa.pub
```

9. **select/highlight** the contents from: ssh-rsa…. all the way to the end and **right click** to copy
10. now add the public key to GitHub profile settings
    1. click on your github avatar on your dashboard page github.com/\<username\>
    2. click Settings
    3. click SSH and GPG keys
    4. click New SSH Key
11. Enter Ctrl+v to paste the copied public key in the Key text box
12. give it a descriptive name like “my laptop” so you know where it is from for the Title
  - e.g. Windows 10 Laptop
13. save the setting
14. Test to see if your system can be authenticated with GitHub

```bash
ssh -T git@github.com
```

- you should see: welcome \<your github username\> ...

## Install miniconda

1. make sure you're on a Terminal
2. type or copy paste the following commands

```bash
cd ~ # change current working directory to user's home directory
curl -o Miniconda3.sh https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
ls # make sure you see Miniconda3.sh file in the current folder
bash  Miniconda3.sh # run the downloaded file with bash program
```

3. follow the instructions on the screen; when you see --More--, just hit space bar key to get the end of the license terms
    - enter **yes** to accept the license terms
    - press **ENTER key** to confirm the default location
    - enter **yes** to initialize Miniconda3
    - close and reopen a Terminal
    - check current conda version installed

```bash
conda --version
```

4. if you see conda command not found error close and start a new bash terminal

```bash
conda update conda # update conda; enter y if asked to update packages
```

## Install notebook and xeus-cling kernel to run C++ code on Jupyter Notebook

1. make sure you're on a Bash Terminal
2. run the following commands

```bash
conda install notebook # Note: it takes a while; if update looks paused, hit enter
conda install -c conda-forge xeus-cling
conda install -c conda-forge jupyter_contrib_nbextensions
conda install -c conda-forge jupyter_nbextensions_configurator
jupyter nbextensions_configurator enable --user
```

## Run Jupyter Notebook server

1. maker sure you are on a Bash Terminal
2. change the working directory to the folder that contains your notebooks or should contain when you create new notebook

```bash
cd <folder with notebook.ipynb files>
jupyter notebook # run jupyter notebook from the current working directory
```

3. if a browser doesn’t open automatically, copy and paste (Ctrl+v) link (just highlight and release mouse) shown on terminal to a browser

## Stop Jupyter Notebook server

1. to stop jupyter notebook, enter control+c keys on the same Terminal that's running Jupyter server

```bash
control+c # press two buttons simultanesouly to stop jupyter notebook server
```
