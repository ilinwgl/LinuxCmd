- change cuda version

    ```
    sudo rm -rf /usr/local/cuda
    sudo ln -s /usr/local/cuda-xx.x /usr/local/cuda
    nvcc --version
    ```

- count the number of files in the current directory
    - exclude subdirectories
    ```
    ls -l | grep "^-" | wc -l
    ```

    - inclue subdirectories
    ```
    ls -lR | grep "^-" | wc -l
    ```