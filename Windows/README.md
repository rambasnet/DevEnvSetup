# Setting up Development Environment on Windows 10

- using Windows Subsystem Layer (WSL) and Ubuntu App

## Tools

- Visual Studio Code
- Ubuntu Bash Terminal
- git version control
- GNU g++ compiler
- Jupyter Notebook
- C++ kernel for Notebook

## Instruction Notes

- **\$** is default prompt for regular user and is always there on Ubuntu Bash Terminal
  - you don't type it as a part of command
- **#** on bash command is comment ignored by the Bash terminal
  - you don't need to type it as a part of command
- any command that starts with **sudo** keyword requires admin (sudo in Linux) priviledge and prompts for your password
- **\< ... \>** - is a place holder that must be completely replaced (including the angular brackets) with actual content in place

## Find Windows 10 username

- you must know your Windows username to complete some of steps
- follow these steps to find your username on Windows

1. on Windows search for Command Prompt app
2. run Command Prompt app and type the following command on prompt, the output is your username

```bash
echo %username%
```

## Install Visual Studio Code

- recommended editor for writing C++ code, compiling and debugging
- editor that has many built-in features including git, terminal and many third party plugins to support many programming languages
- follow the instruction provided in [VSCodeInstall/VSCode-Install-README.md](VSCodeInstall/VSCode-Install-README.md)

## Install Ubuntu App

- follow the instruction provided in [WSL/WSL-Install-README.md](WSL/WSL-Install-README.md)

## Run Ubuntu Bash Terminal/Shell

- any time you need to run Ubuntu Bash Terminal (also called Shell), follow this step
    1. search and run Ubuntu
    ![Run Ubuntu](WSL-Run-Ubuntu.png)

## Install C++ Compiler and relevant tools

1. make sure you're on Ubuntu Bash Terminal
2. run the following commands on Bash Terminal

```bash
sudo apt install build-essential #installs compiler and many other relevant tools
sudo apt install ccache # compiler cache - speeds up compiling the same source files many
g++ --version # check if g++ is installed
```



## Install miniconda on Ubuntu

1. make sure you're on Ubuntu Bash Terminal
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
    - close and reopen Ubuntu Bash Terminal
    - check current conda version installed

```bash
conda --version
```

4. if you see conda command not found error close and start a new bash terminal

```bash
conda update conda # update conda; enter y if asked to update packages
```

## Install notebook and xeus-cling kernel to run C++ code on Jupyter Notebook

1. make sure you're on Ubuntu Bash Terminal
2. run the following commands

```bash
conda install notebook # Note: it takes a while; if update looks paused, hit enter
conda install -c conda-forge xeus-cling
conda install -c conda-forge jupyter_contrib_nbextensions
conda install -c conda-forge jupyter_nbextensions_configurator
jupyter nbextensions_configurator enable --user
```

## Run Jupyter Notebook server

1. maker sure you are on Ubuntu Bash Terminal
2. change the working directory to the folder that contains your notebooks or should contain when you create new notebook

```bash
cd <folder with notebook.ipynb files>
jupyter notebook # run jupyter notebook from the current working directory
```

3. if a browser doesn’t open, copy and paste (Ctrl+v) link (just highlight and release mouse) shown on terminal to a browser

## Stop Jupyter Notebook server

1. to stop jupyter notebook, enter control+c keys on the same Terminal that's running Jupyter server

```bash
control+c # press two buttons simultanesouly to stop jupyter notebook server
```

## Access Windows C: drive and files from Ubuntu Bash Terminal

1. make sure you're on Ubuntu Bash Terminal
2. type the following command

```bash
cd  /mnt/c/Users/<your windows username>
```
