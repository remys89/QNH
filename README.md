# Docker workshop

In front of you there is a laptop with Docker toolbox installed.
During the following exercises, you will learn to get along with Docker in the basic way of working, and be able to deploy small containers.
If you have any questions, feel free to ask.

## Basics

First, learn to get started with Docker after our presentation.
We are going to deploy a Busybox container on our docker environment.
Busybox is a small linux environment and a sandbox to play with.

_docker pull busybox_

```sh
$ docker pull busybox
Using default tag: latest
latest: Pulling from library/busybox
```

This way, we will download the image to our docker machine so its ready for use in a container.
Check if the image is correctly downloaded.

_docker images_

```sh
$ docker images
REPOSITORY                TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
busybox                   latest              sha256:47bcc        10 weeks ago        1.113 MB
```

Ok, we are fine. 
Now, lets try and start a container with this image, and use hello world as echo command:

_docker run busybox echo "hello world"_

Check your output:

```sh
$ docker run busybox echo "hello world"
hello world
```

Now, check the status of the containers with the docker ps command

_docker ps_

What do you see ?
Right, nothing. Thats because the container was executed with the hello world command, and then exited.
Add the "-a" flag.

_docker ps -a_

Should be somehow the following output:

```sh
$ docker ps -a
CONTAINER ID        IMAGE                     COMMAND                CREATED             STATUS                     PORTS               NAMES
901765e0ec64        busybox                   "echo 'hello world'"   2 minutes ago       Exited (0) 2 minutes ago                       backstabbing_liskov
```
