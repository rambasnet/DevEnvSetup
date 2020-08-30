# Using Git

- Git can be used with various Graphical User Interface (GUI)-based applications or using Command Line Interface (CLI)
- VS Code provides GUI interface to work with your git repository
- GUI interface makes it easy to work with git repository (e.g. add, commit, push, pull, etc.)
- command line is an alternative and this document provides instructions for both GUI and Command line interface of git
- Git must be configured, before the GUI or CLI can be used to work with your repository

## Git GUI Interface on VS Code

1. open VS Code on your system
    - Note that Windows WSL Ubuntu must have Remote-WSL extension installed to access files from Windows as well as WSL Ubuntu
2. display Integreted Terminal on VS Code
    - click Terminal menu and click New Terminal
    - select bash as the default shell
3. open your repository
    1. click File -> Open Folder and browse the repository folder that's cloned on the system
    - click Show Local if the repository is cloned on Windows system
    - by default it'll show folders and files on WSL Ubuntu system
    - e.g. if CS1-rbasnet is the repository cloned in user's home directory
    - hit OK button once you found your repo to open it
    ![Open Repo](Code-Git-GUI.png)
3. create a test folder and file
    1. click Explorer and create a test folder and test.txt file inside it, if you hover your mouse on repository name, you'll see New File and New Folder buttons
    - write some text to the test.txt file and save the file
    ![Create Folder](CreateFolderFile.png)
4. track changed files and commit changes to the local repository
    1. click Source Control icon on the left panel
    2. click + on each file that you want to stage changes
    3. write some message in the text box
    4. click check button to commit locally
    ![Add, Commit](GUI-add-Commit.png)
5. push changes to the remote repository (GitHub.com)
    - click more ... buttom and select Pull, Push -> Push
    ![Push](GUI-push.png)
6. Check your GitHub.com repository and make sure you see test folder and test.txt file
    - if you're on the repo page, you'll need to refresh/reload the page
    ![GitHub Check](GitHubCheck.png)
6. when workin in team or want to work from different system, you must first pull to avoid conflicts
    1. click ... more button on Source Control panel.
    2. click Pull, Push and click Pull

## CLI Git commands

- open Bash Terminal separately or Integrated Terminal on VS Code
- current working director must be repositry's root folder to issue git commands
- the most commonly used commands are: add, commit, push and pull

    ```bash
    cd <repository folder>
    git status # check the status
    git add <add new or modified file shown in red>
    git commit -m "write a brief message"
    git push # send/upload the updates to remote repo
    git status # make sure everything is uptodate
    git pull # pull/dowloand updates from remote repo
    ```

![CLI Git](Git-CLI.png)

- confrim the remote repository on GitHub is uptodate
