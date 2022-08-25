# Installing Miniconda Python3 Package Manager on Mac

- miniconda install provides Python3 as well
- miniconda can be used to install various other Python packages such as jupyter notebook, machine learning libraries, etc.

1. open a Terminal
2. find out if your Mac is running Intel or Apple M1/M2 that's based on ARM64 architecture and follow either 3.a or 3.b based on the result

```bash
   uname -m
```

3.a if the result of `uname -m` is **x86_64**, type or copy paste the following commands

```bash
cd ~ # change current working directory to user's home directory
curl -o Miniconda3-intel.sh https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
ls # make sure you see Miniconda3.sh file in the current folder
bash  Miniconda3-intel.sh # run the downloaded file with bash program
```

![Miniconda Install](Miniconda-Install.png)

3.b if the result of `uname -m` is **arm64**, type or copy paste the following commands

```bash
cd ~ # change current working directory to user's home directory
curl -o Miniconda3-arm64.sh https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
ls # make sure you see Miniconda3.sh file in the current folder
bash  Miniconda3-arm64.sh # run the downloaded file with bash program
```

4. follow the instructions on the screen; when you see :, just hit space bar key to get the end of the End User License Agreement and see >>>
    - enter **yes** to accept the license terms
    - press **ENTER key** to confirm the default location
        - this may take a while
    - enter **yes** to initialize Miniconda3

5. close and reopen Terminal once Miniconda3 is installed
6. check current conda version installed

    ```bash
    conda --version
    ```

    - if you see conda command not found error close and start a new bash terminal and type the command again

7. check python installed

    ```bash
    python --version # you should see Python 3.x.x
    ```

8. update conda

    ```bash
    conda update conda
    ```

    - enter **y** if asked to Proceed

