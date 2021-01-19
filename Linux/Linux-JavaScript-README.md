# Setting up JavaScript (NodeJS) Development Environment on Ubuntu Linux

## Tools

- Visual Studio Code
- git version control
- Python3
- NodeJS
- Jupyter Notebook

## Install Visual Studio Code

- recommended editor for writing C++ code, compiling and debugging
- editor that has many built-in features including git, terminal and many third party extensions to support many programming languages and dev tools
- download and install VS Code for Ubuntu (.deb) from [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

## Run Bash Terminal/Shell

1. search and run Terminal
2. add it to favourites for quick access

## Install Git

- follow the instructions in [../Git/README.md](../Git/README.md)

## Configure Git

- follow the instructions in [../Git/Git-Config-README.md](../Git/Git-Config-README.md)

## Install miniconda Python Package Manager

- follow the instructions in [Miniconda-README.md](Miniconda-README.md)


## Install NodeJS and Tools

```bash
conda update conda
conda create -n nodejs
conda env list
conda activate nodejs
conda install -c conda-forge nodejs
conda install jupyter
conda install -c conda-forge jupyter_contrib_nbextensions
conda install -c conda-forge jupyter_nbextensions_configurator
jupyter nbextensions_configurator enable --user
npm install -g ijavascript
ijsinstall
```

## Run Jupyter Notebook server

1. run Bash Terminal
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
