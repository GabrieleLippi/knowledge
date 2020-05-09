Docker is not a Virtual Machine. The main difference is that Docker doesn't need
a **hypervisor** and can communicate directly with the **host operating system**
through the **docker daemon**

The docker client connects to docker server through REST api.

The docker daemon and cli are both written in **go** and [open source](https://github.com/docker)

The server running the docker daemon is referred to as the **DOCKER_HOST**

## Docker CE
>Docker Community Edition

free and open source, has the same core feauters as enterprise edition.
is production ready.
two release channel:
  * **edge** releases every 1 month
  * **stable** releases every 3 month, will receive patche for 4 months after
    release


## Docker EE
>Docker Enterprise Edition

1. certified images and plugins
2, Docker DataCenter
3. Vulnerability scans
4. Official support

From 750$ to 2000$ per year

## Docker Hello World

1. the Docker client contact the Docker daemon.
2. the Docker daemon **pulls** the image "hello-world", as it can't find it
   locally. The way it pulls it's similar to the way git works, pulling only
   the delta.
3. the Docker daemon **creates** a new container from that image which runs the
   executable that produces the output the user reads.
4. the Docker daemon **streams** the output to the Docker client, which sends it
   to the terminal
