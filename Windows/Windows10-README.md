# Setting up C++ Development Environment on Windows 10

- using Windows Subsystem Layer (WSL) and Ubuntu App

## Tools
- Visual Studio Code
- Ubuntu Bash Terminal
- git version control
- g++ compiler
- Jupyter Notebook
- c++ kernel for Notebook

## Install Visual Studio Code
- recommended editor for writing C++ code, compiling and debugging
- download and install the right version for your machine from here:
   [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
- editor that has many built-in features including git, terminal and many third party plugins to support many programming languages

## Install Ubuntu App
- Windows 10 allows Ubuntu installation as an app


1. turn Windows Subsystem for Linux feature on following these steps:
    1. search for "Turn Windows features on or off" without quotes
    2. run the Windows Feature app
    3. find and check Windows Subsystem for Linux towards the bottom of the list
    4. click ok button
        - Note, it may take a while
    5. restart your computer
    
2. install Ubuntu App following these steps:
    1. search for Microsoft Store
    - run the Store
    - search Ubuntu and click install/get it 
        - Note, it may take a while
3. when prompted, pick username and password
    - pick simple easy to remember username (e.g. user) and password (e.g. user)
    - this password is required to install other tools on Ubuntu
    - when entering password, you'll not see any feedback (* or dots); that's the Linux way of hiding password
    - just type password in the dark and hit enter; believe me it'll work!
    
## Run Ubuntu Bash Terminal
- any time you need to run Ubuntu Bash Terminal - the black window that will say something like
    ```bash
    user@DESKTOP-...: ~$
    ```
    follow these steps:
    1. search Ubuntu
    2. click Ubuntu icon to run the Terminal
    
#### Note:
- **\$** is default prompt and is always there on Bash terminal
    - you don't type it as a part of command
- **#** is comment ignore by the Bash terminal
    - you don't need to type it as a part of command
- any command that starts with **sudo** keyword requires admin access and prompts for your password

### Update Ubuntu
- make sure you're on Ubuntu Bash Terminal; see above if not sure how
- type the following commands
- see Note above regarding **$** prompt and **#** comment symbols on Bash Terminal

```bash
$ cd ~ # change current working directory to user's home directory
$ sudo apt update # update Ubuntu app; will ask you to type your password
```

### Install g++ compiler and relevant tools
- make sure you're on Ubuntu Bash Terminal
- run the following commands on Bash Terminal

```bash
$ sudo apt install build-essential 
$ sudo apt install ccache # compiler cache - speeds up compiling the same source files many
$ g++ --version # check if g++ is installed
```

## Install git client
- make sure you're on Ubuntu Bash Terminal
- git should be already installed; double check

```bash
$ git --version
```
- If you get error, install git typing the following command
```
$ sudo apt install git
```

## Configure Git using ssh keys
- using ssh keys is not required but is recommended as it let's you authenticate with GitHub server or other git repo hosting sites so you don't have to type username/password all the time
    - and YES, you'll be have to authenticate quite frequently while pulling and pushing code from the server
    - ssh keys will make your life lot easier
- these steps you do once on each system you are using Git on


1. make sure you're on Ubuntu Bash Terminal
2. let git know who you are; use your real name and email you registered on GitHub
    - double quotes are required  
    ```bash
    $ git config --global user.name "John Doe"
    $ git config --global user.email "johndoe@domain.com"
    ```
3. check if you've public/private key pair already genereted
    ```bash
    $ ls ~/.ssh/  # list the contents of ~/.ssh/ folder
    ```
    
3. if you see id_rsa id_rsa.pub files, you have public/private key pairs, so you don't have to generate one
    - skip step 4
4. if no key pair exists, generate one
    - pick default location to save the key and just hit enter key for password (or do not use password!)
    - simply hit enter until you get the **\$** prompt back
    
    ```bash
    $ ssh-keygen
    ``` 
5. copy the public/private keys to the Windows 10 System
    - since Visual Studio Code is installed on Windows and it provides GUI-based git, it’s nice to be able to utilize it when you’re tired of the command line git
    
6. check if the ssh keys exist on windows so you don’t overwrite them
    - if you're not sure what your Windows username is, see the section Finding Windows 10 username below
    - replace including \< ... \> with your Windows username
    
```bash
$ ls /mnt/c/Users/<your Windows username>/.ssh/
```

7. if you see ls cannot access … No such file or directory message, copy the keys using the following command and skip next step

```bash
$ cp -r  ~/.ssh/  /mnt/c/Users/<your windows username>
```
8. if you see id_rsa id_rsa.pub files with the previous command, copy with keys with different names

```bash
$ cp ~/.ssh/id_rsa.pub /mnt/c/Users/<your windows username>/.ssh/id_rsa.pub
$ cp ~/.ssh/id_rsa /mnt/c/Users/<your windows username>/.ssh/id_rsa
```
9. list the content of the public key to copy to GitHub
    - **select** the contents from: ssh-rsa…. all the way to the end and **right click** to copy
```bash
$ cat ~/.ssh/id_rsa.pub
```
- now add the public key to GitHub profile settings
    1. click on your github avatar on your dashboard page https://github.com/<username>
    2. click Settings
    3. click SSH and GPG keys 
    4. click New SSH Key
- Enter Ctrl+v to paste the copied public key in the Key text box
- give it a descriptive name like “my laptop” so you know where it is from for the Title
    - e.g. Windows 10 Laptop
    - save the setting
- Test to see if your system can be authenticated with GitHub
    ```bash
    $ ssh -T git@github.com
    ```
    - if you see: welcome <your github username>..., you’re good!

### Install miniconda on Ubuntu
1. make sure you're on Ubuntu Bash Terminal
- type or copy paste the following commands

```bash
$ cd ~ # change current working directory to user's home directory
$ curl -o Miniconda3.sh https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh 
$ ls # make sure you see Miniconda3.sh file in the current folder
$ bash  Miniconda3.sh # run the downloaded file with bash program
```

- follow the instructions on the screen; when you see --More--, just hit space bar key to get the end of the license terms
- enter **yes** to accept the license terms
- press **ENTER key** to confirm the default location
- enter **yes** to initialize Miniconda3
- close and reopen Ubuntu Bash Terminal
- check current conda version installed

```bash
$ conda --version
```

- if you see command not found error, run the following command, or close and start a new bash terminal

```
$ conda update conda # update conda
```
- enter **y** if asked to update packages


### Install notebook and xeus-cling kernel to run C++ code on Jupyter Notebook
- make sure you're on Ubuntu Bash Terminal

```bash
$ conda install notebook # Note: takes a while; if screen seems to be paused, hit enter
$ conda install -c conda-forge xeus-cling
$ conda install -c conda-forge jupyter_contrib_nbextensions
$ conda install -c conda-forge jupyter_nbextensions_configurator
$ jupyter nbextensions_configurator enable --user
```

### Run Jupyter Notebook server
- maker sure you are on Ubuntu Bash Terminal
- change the working directory to the folder that contains your notebooks or should contain when you create new notebook
    
```bash
$ cd <folder With Notebook>
$ jupyter notebook
```
-     
if a browser doesn’t open, copy and paste (Ctrl+v) link (just highlight and release mouse) shown on terminal to a browser
- to stop jupyter notebook, enter ctrl+c on the same Terminal that's running notebook
```bash
$ ctrl+c # stop jupyter notebook server
```

### Accessing Windows C: drive from Ubuntu Bash Terminal
- run Ubuntu Bash Terminal and type the following commands

```bash
$ cd  /mnt/c/Users/<your windows username>
```

### Find Windows 10 username
- on Windows search for Command Prompt app
- run Command Prompt app and type the following command on prompt, the output is your username
```bash
echo %username%
```