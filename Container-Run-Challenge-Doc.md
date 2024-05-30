# Solution to the Running Container Challenge in the DIVEINTO CLOUD NATIVE COURSE BY JAMES SPURIN

## Challenge 1

To create and run a container using the Ubuntu container image. 

1. Create and Run a Container 
Use the command to pull an image if it isn't present and create a new container from the Ubuntu image. we will start a bash session inside the container. 

```bash 
docker run -it ubuntu bash 
```
![Ubuntu container](<Image/SC 01 - Run Container Ubuntu.PNG>)

2. To install 'nano' or 'vim' and 'htop'. we will need to make use of the `apt` package management tools to complete the task. 
![install apt](<Image/SC 02 - apt package manager install.PNG>)

Next we will install `vim`, `nano` and `htop`
1. Nano 
![install nano](<Image/SC 03 - install nano.PNG>)

2. VIM 
![install Vim](<Image/SC 04 Install Vim.PNG>)

3. Htop
![install htop](<Image/SC 05 - Install htop.PNG>)

To check the list of containers running, use the command 

```bash 
docker ps -a 
```
![running container](<Image/SC 06 - List of container running.PNG>)


## Challenge 2 

We will repeat the first challenge but use the amazonlinux image which is based on CentOS. 

1. Create and Run a Container
Use the command 
```bash 
docker run -it amazonlinux bash 
```
![Run Container amazonlinux](<Image/SC 07 Amazonlinux.PNG>)

2. To install 'nano' or 'vim' and 'htop'. we will need to make use of the `yum` package management tools to complete the task. 

![install yum](<Image/SC 08 - yum Update.PNG>)

Next we will install `vim`, `nano` and `htop`

1. Vim 
![install vim](<Image/SC 09 - Yum install vim.PNG>)

2. Nano 
![install nano](<Image/SC 10 - yum install nano.PNG>)

3. htop 
![install htop](<Image/SC 11 yum install htop.PNG>)

To check the list of containers running, use the command 

```bash 
docker ps -a 
```
![Running Container](<Image/SC 12 - Runing Container.PNG>)

Cleaning up the exited containers

Use the command 

```bash 
docker rm <container_name>
```
![Clean up ](<Image/SC 13- Cleaning up Container.PNG>)


## Challenge 3 

Run a ubuntu container that will automatically clean up after itself, we don't need to use `-it` as we will only be running a single command. we can use the `--rm` flag to ensure the container is removed after it exits. 

The command `cat /etc/os-release` is to run inside the container, which will display information about the OS version.

The command below will pull the latest Ubuntu image (if not already available), run the specified command, display the OS release information, and then clean up the container by removing it automatically.

```bash 
docker container run --rm ubuntu:latest cat /etc/os-release
``` 

**TROUBLESHOOTING** 
While running the command above, I got an error message 

![Error message](<Image/SC 14 - Error Message.PNG>)

The command might have been run in a context where the `cat` command tried to access a file on the host computer rather than within the container. To resolve this, run the command in a your terminal (power shell, command prompt or Linux terminal) rather than on Git Bash. 

![Final result](<Image/SC 15 - Powershell result.PNG>)

## Challenge 4 

Run Amazonlinux container that will automatically clean up after itself, we don't need to use `-it` as we will only be running a single command. we can use the `--rm` flag to ensure the container is removed after it exits. 

The command `cat /etc/os-release` is to run inside the container, which will display information about the OS version.

The command below will pull the latest amazonlinux image (if not already available), run the specified command, display the OS release information, and then clean up the container by removing it automatically.

```bash 
docker container run --rm amazonlinux:latest cat /etc/os-release
``` 

![amazonlinux OS release](<Image/SC 16 amazonlinux OS release.PNG>)

## Challenge 5 

Use the `docker rmi` command followed by the image name and tag, or the Image ID, to remove the ubuntu image

```bash 
docker rmi ubuntu:lastest
```
![remove ubuntu](<Image/SC 17 Remove Ubuntu.PNG>)

## Challenge 6 

To remove the Amazonlinux container image using the alternative Docker command line approach, we use `docker image rm` command. 

```bash 
docker image rm amazonlinux:latest
```
![remove amazonlinux](<Image/SC 17 Remove Ubuntu.PNG>)