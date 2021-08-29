# Development Evnvironment Setup Instructions on Windows 10

If you're running Windows 10, follow the instructions in this section. Windows instructions use WSL Ubuntu Bash Terminal to install Linux-based tool chains.

NOTE: Certain tool chains may not work with WSL. So, it's highly recommended that you first install Ubuntu Linux Virtual Machine (VM) and follow the instruction for Linux development environment setup. In order to run VM smoothly, your system must have atleast 8 GB RAM and 4 cores so you can allocate half of the resources (4GB RAM and 2 cores -- ideal amount) to your VM. Alternativley, you can format and install Ubuntu Linux as the host Operating System especially if your system doesn't have adequate resources.

## C++ Dev Environment Setup on Personal Windows System

- follow the instructions on [Windows-CPP-README.md](Windows-CPP-README.md) to setup C++ Dev Environment on Windows

## Python3 Development Environment Setup on Personal Windows System

- follow the instructions on [Windows-Python3-README.md](Windows-Python3-README.md) to setup Python Dev Environment on Windows

## Install WSL on CMU Labs Windows 10 System

- On CS Labs Windows 10 System, follow these instructions:

- NOTE: Pick a system and stick to it for the rest of the semester! Otherwise, you may have to install WSL and all the tools on every system you use.

1. Double click/run WSL shortcut on your Desktop or search for WSL

2. Click Install and go through the installation process enter yes on every prompt! It may take several minutes.

4. Once everything is installed and you get bash terminal, type the following command to update your Linux

    ```bash
    apt update
    ```

5. Once WSL is installed, you can click WSL desktop shortcut and then just run shell next time around to use the Bash Terminal

6. Map F: drive to Ubuntu file system

    ```bash
    mkdir -p /mnt/f
    mount -t drvfs '\\homefs\home\<mav_username>' /mnt/f
    ls /mnt/f
    ```

Note: [username] = your username without `< >`

    - You should see all your personal F: drive files and folders if mapped correctly

7. Your C: drive is already mounted at `/mnt/c`

    ```bash
    ls /mnt/c
    ```

8. VS Code is already installed on CS Lab computers
9. Follow the rest of the instructions on [Windows-CPP-README.md](Windows-CPP-README.md) to setup C++ Dev Environment including g++ compilers, git, jupyter notebook, etc.
