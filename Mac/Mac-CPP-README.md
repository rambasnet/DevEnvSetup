# Setting up C++ Development Environment on Mac

## Tools

- Visual Studio Code
- git version control
- g++ compiler
- Jupyter Notebook
- C++ kernel for Jupyter Notebook

## Install Visual Studio Code

- recommended editor for writing C++ code, compiling and debugging
- editor that has many built-in features including git, terminal and many third party plugins to support many programming languages
- download and install VS Code for Mac from [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

## Configure Visual Studio Code

- follow the instructions found in [../VSCode/VSCode-CPP-README.md](../VSCode/VSCode-CPP-README.md)

## Run Bash Terminal

- any time you need to run bash commands, you must do it from Terminal app

1. follow these steps to run Terminal
2. search (using command+space bar keys) for Terminal
3. click to run Terminal App
4. Right click Terminal app on dock -> Options -> Keep in Dock (for quick access in the future)

## Install command-line developer tools (g++, git, etc.)

1. open a Terminal
2. run the following commands on the Terminal

  ```bash
  x-code-select install #installs compiler and many other relevant command-line tools
  g++ --version # check if g++ is installed
  git --version # check if git is installed
  ```

## Configure Git

- the instruction is virtually the same for WSL Ubuntu and Mac
- follow the instructions on [../Git/Git-Config-README.md](../Git/Git-Config-README.md)

## Install miniconda Python3 package manager

- follow the instructions on [Mac-Miniconda-README.md](Mac-Miniconda-README.md)

## Install Jupyter Notebook and C++ Kernel

- follow the instructions on [../Linux/Jupyter-README.md](../Linux/Jupyter-README.md)

## Run Jupyter Notebook server

1. open a Terminal
2. change the working directory to the folder that contains your notebooks or should contain when you create new notebook

    ```bash
    cd <folder with notebook.ipynb files>
    jupyter notebook # run jupyter notebook from the current working directory
    ```

3. if a browser doesn’t open automatically, copy and paste (Ctrl+v) link (just highlight and release mouse) shown on terminal to a browser

## Stop Jupyter Notebook server

1. to stop jupyter notebook, enter control C keys simultaneously on the same Terminal that's running Jupyter server
2. do it a few times if it doesn't stop

    ```bash
    press control C keys
    ```
