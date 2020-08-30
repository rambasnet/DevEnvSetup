# Install Jupyter Notebook

- install notebook and xeus-cling kernel to run C++ code on Jupyter Notebook for teaching and learning C++

1. run Bash Terminal
2. run the following commands

    ```bash
    conda install notebook # Note: it takes a while; if update looks paused, hit enter
    conda install -c conda-forge xeus-cling
    conda install -c conda-forge jupyter_contrib_nbextensions
    conda install -c conda-forge jupyter_nbextensions_configurator
    jupyter nbextensions_configurator enable --user
    ```

    - enter **y** to proceed when asked on the installation steps
