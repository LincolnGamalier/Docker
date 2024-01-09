# Docker

**Instalação do Docker - Ubuntu**

lincoln@UbuntuHML:~$ sudo su
[sudo] password for lincoln: 
root@UbuntuHML:/home/lincoln# 
root@UbuntuHML:/home/lincoln# 
root@UbuntuHML:/home/lincoln# sudo apt install docker.io
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  bridge-utils containerd git git-man liberror-perl pigz runc ubuntu-fan
Suggested packages:
  ifupdown aufs-tools btrfs-progs cgroupfs-mount | cgroup-lite debootstrap
  docker-doc rinse zfs-fuse | zfsutils git-daemon-run | git-daemon-sysvinit
  git-doc git-email git-gui gitk gitweb git-cvs git-mediawiki git-svn
The following NEW packages will be installed:
  bridge-utils containerd docker.io git git-man liberror-perl pigz runc
  ubuntu-fan
0 upgraded, 9 newly installed, 0 to remove and 176 not upgraded.
Need to get 73,5 MB of archives.
After this operation, 287 MB of additional disk space will be used.
Do you want to continue? [Y/n] y

**Docker Instalado**

ocker version 24.0.5, build 24.0.5-0ubuntu1~22.04.1
root@UbuntuHML:/home/lincoln# docker

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

.
.
.
.
.

**Procurando imagens dentro do container**
root@UbuntuHML:/home/lincoln# docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES


**Instalando imagem**
(Exemplo usado --Hello World--)

latest: Pulling from library/hello-world
c1ec31eb5944: Pull complete 
Digest: sha256:ac69084025c660510933cca701f615283cdbb3aa0963188770b54c31c8962493
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/


**Imagem instalada*

root@UbuntuHML:/home/lincoln# docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
f9b8cf4108c4   hello-world   "/hello"   12 seconds ago   Exited (0) 11 seconds ago             adoring_faraday

root@UbuntuHML:/home/lincoln# docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
hello-world   latest    d2c94e258dcb   8 months ago   13.3kB

**Instalando uma outra imagem**
(Postgres)

root@UbuntuHML:/home/lincoln# docker run postgres
Unable to find image 'postgres:latest' locally
latest: Pulling from library/postgres
af107e978371: Pull complete 
4dab593eebe3: Pull complete 
4998fa695fba: Pull complete 
68722367c502: Pull complete 
f94fde538ad8: Pull complete 
083cda9930f9: Pull complete 
d17e28f1e487: Pull complete 
60abce37aea7: Pull complete 
dc71bc844158: Pull complete 
8af67c1d8689: Pull complete 
a3a37d60b464: Pull complete 
a28cd92dbadf: Pull complete 
ebba832273a7: Pull complete 
ca09208e18c7: Pull complete 
Digest: sha256:b09f2562ab14fcae750cfc5ae457cd97e90c37679f520bc4a84180913de90261
Status: Downloaded newer image for postgres:latest
Error: Database is uninitialized and superuser password is not specified.
       You must specify POSTGRES_PASSWORD to a non-empty value for the
       superuser. For example, "-e POSTGRES_PASSWORD=password" on "docker run".

       You may also use "POSTGRES_HOST_AUTH_METHOD=trust" to allow all
       connections without a password. This is *not* recommended.

       See PostgreSQL documentation about "trust":
       https://www.postgresql.org/docs/current/auth-trust.html

root@UbuntuHML:/home/lincoln# docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
postgres      latest    bdc467e80232   4 days ago     425MB
hello-world   latest    d2c94e258dcb   8 months ago   13.3kB