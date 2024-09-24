# ros1_docker

## Quick Start
Run the docker container. Add the `--rm` option depending on the situation.    
※ If you do not want to save your changes, it is recommended to use the `--rm` option.
### 1. Build Image
```
cd your-path/ros1_docker
./build.sh
```
### 2. Docker Run
- use gpu
```
xhost +local:
./run_gpu.sh
```
- without gpu
```
./run.sh
```

## After the second
launch (Rename containers as necessary)
```

xhost +local:
docker start my-noetic
```
login
```
./login.sh
```
close (Rename containers as necessary)
```

docker stop my-noetic
```
## File sharing (hotst <---> docker)
The folder ~/ros2_docker/docker_share on the host PC and the folder ~/host_files on docker are bind-mounted.  
You can communicate in both directions. However, if something in the folder is deleted, it will be reflected in both.
![Screenshot from 2023-10-14 21-36-14](https://github.com/masakifujiwara1/ros2_docker/assets/72371743/b3142be3-44d8-4581-b2b0-de0aa8658865)

## Default config files
### .bashrc
The commands are introduced below.
- rs : cd ~/ros2_ws/src
- bashrc : source ~/.bashrc
- ros_make : colcon build --symlink-install is executed no matter what directory you are in
### .vimrc
- set number

## Build (option)
If you want to customize `.bashrc` or `.vimrc`, please change the files in config/.  
After the change, execute the following command.  
※ We recommend replacing files with [file sharing](https://github.com/masakifujiwara1/ros2_docker/blob/main/README.md#file-sharing-hotst-----docker).

```
./build.sh
```