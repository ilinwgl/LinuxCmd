- 更改cuda toolkit 版本

    ```
    sudo rm -rf /usr/local/cuda
    sudo ln -s /usr/local/cuda-xx.x /usr/local/cuda
    nvcc --version
    ```
- 更改 gcc g++ 版本
  ```
  sudo add-apt-repository ppa:ubuntu-toolchain-r/test
  sudo apt-get update
  sudo apt install gcc-X
  sudo apt install g++-X
  ```

  update the alternatives for compilers
  ```
  #Remove the previous alternatives
  sudo update-alternatives --remove-all gcc
  sudo update-alternatives --remove-all g++

  #Define the compiler
  sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-X priority-number(30)
  sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-X priority-number(30)

  sudo update-alternatives --install /usr/bin/cc cc /usr/bin/gcc priority-number(30)
  sudo update-alternatives --set cc /usr/bin/gcc

  sudo update-alternatives --install /usr/bin/c++ c++ /usr/bin/g++ priority-number(30)
  sudo update-alternatives --set c++ /usr/bin/g++

  #Confirm and update (You can use the default setting)
  sudo update-alternatives --config gcc
  sudo update-alternatives --config g++
  ```

- 统计文件夹下文件数量
    - 不包含子目录
    ```
    ls -l | grep "^-" | wc -l
    ```

    - 包含子目录
    ```
    ls -lR | grep "^-" | wc -l
    ```

- 查看文件权限以及目录信息等
    ```
    ls -a 列出目录所有文件，包含以.开始的隐藏文件
    ls -A 列出除.及..的其它文件
    ls -r 反序排列
    ls -t 以文件修改时间排序
    ls -S 以文件大小排序
    ls -h 以易读大小显示
    ls -l 除了文件名之外，还将文件的权限、所有者、文件大小等信息详细列出来
    ```

- cat 指令
  - 显示整个文件
    ```
    cat filename
    ```

  - 从键盘创建一个文件
    ```
    cat > filename
    ```

  - 将几个文件合并成一个文件
    ```
    cat file1 file2 > file
    ```

- df 指令
  
    显示磁盘空间使用情况。获取硬盘被占用了多少空间，目前还剩下多少空间等信息，如果没有文件名被指定，则所有当前被挂载的文件系统的可用空间将被显示。
    
    默认情况下，磁盘空间将以 1KB 为单位进行显示，除非环境变量 POSIXLY_CORRECT 被指定，那样将以512字节为单位进行显示

    ```
    df -a 全部文件系统列表
    df -h 以方便阅读的方式显示信息
    df -i 显示inode信息
    df -k 区块为1024字节
    df -l 只显示本地磁盘
    df -T 列出文件系统类型
    ```

- du 指令
    du 命令也是查看使用空间的，但是与 df 命令不同的是 Linux du 命令是对文件和目录磁盘使用的空间的查看

    ```
    du -a 显示目录中所有文件大小
    du -k 以KB为单位显示文件大小
    du -m 以MB为单位显示文件大小
    du -g 以GB为单位显示文件大小
    du -h 以易读方式显示文件大小
    du -s 仅显示总计
    du -c 或 --total  除了显示个别目录或文件的大小外，同时也显示所有目录或文件的总和
    ```