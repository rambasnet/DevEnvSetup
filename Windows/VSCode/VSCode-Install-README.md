# Visual Studio (VS) Code Installation Instruction on Windows

## Install VS Code on Windows

1. find the system type (32bit or 64bit or ARM) of your Windows system
    1. search and run "This PC" -> Properties
    ![This PC Properties](PCProperties.png)
    2. note system type
    ![System Type](SystemType.png)

2. download the right version of VS Code installer for your machine from here
    1. on your browser go to [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

    2. if your system type is 32-bit, click 32 bit and if your system is 64-bit download 64-bit System Installer
    ![VS Code Installer](CodeInstaller.png)

3. run the dowloaded Installer program and follow the Setup wizard
    1. select "I Accept the agreement"
    2. select default destination folder
    ![Destination](CodeDestination.png)
    ![Start Menu](StartMenu.png)
    ![Additional Tasks](AdditionalTasks.png)
    ![Install](InstallStep.png)

## Launch VS Code App from Windows

1. run Ubuntu App/WSL to run Bash Termimal
2. enter the following command on Bash Terminal

    ```bash
    code .
    ```

## Configure VS Code for WSL Ubuntu

- if VS Code is configured properly both Ubuntu files and folders and Windows file system can be accessed easily from VS Code File -> Open Menu

1. run Ubuntu App to run Bash Termimal
2. enter the following command

    ```bash
    code .
    ```

4. install Remote - WSL extension from Microsoft in WSL:Ubuntu
    - click on Extensions icon on the left pane
    - search Remote WSL
    - install Remote WSL by Microsoft
    ![Remote WSL Install](Remote-WSL.png)

5. Note that when VS Code is ran from WSL Ubuntu, you should see WSL:Ubuntu on the bottom left
    ![WSL:Ubuntu](WSL-Code.png)

## Launch VS Code App with Remote Extension

1. open Ubuntu Bash Termimal
2. enter the following command on the Ubuntu Bash Terminal

    ```bash
    code .
    ```
3. you should see WSL:Ubuntu on the bottom left
    ![WSL:Ubuntu](WSL-Code.png)

## Configure Integreted Terminal on VS Code

- follow the instructions on [VSCode-Terminal-README.md](VSCode-Terminal-README.md)
