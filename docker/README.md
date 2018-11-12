# Docker command line

## These Docker commands are essential

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)

* [docker run](https://docs.docker.com/engine/reference/commandline/run/)

* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

| repository hub | local repository | contaier                  | rootfs        | info           |
| -------------- | ---------------- | ------------------------- | ------------- | -------------- |
| docker login   | docker images    | docker ps                 | docker commit | docker info    |
| docker pull    | docker rmi       | docker inspect            | docker cp     | docker version |
| docker push    | docker tag       | docker top                | docker diff   |
| docker search  | docker build     | docker attach             |
|                | docker history   | docker events             |               |
|                | docker import    | docker logs               |
|                | docker save      | docker wait               |               |
|                |                  | docker start/stop/restart |
|                |                  | docker exec               |
|                |                  | docker run                |
|                |                  | docker pause/unpause      |
|                |                  | docker rm                 |
|                |                  | docker kill               |
|                |                  | docker create             |
|                |                  | docker port               |
|                |                  | docker export             |

## artifactory下拉取镜像

> docker pull artifactory.swdc.saurer.com:443/docker/[serviceName]:latest

artifactory.swdc.saurer.com:443/docker/docker/lion-user-service

## docker UI 的可视化工具

* dockerUI

    ``` docker
    docker pull uifd/ui-for-docker

    docker run -it -d --name docker-web -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock docker.io/uifd/ui-for-docker

    docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock dockerui/dockerui
    ```
    > localhost:9000

* shipyard

    ``` docker
    docker run --rm -v /var/run/docker.sock:/var/run/docker.sock shipyard/deploy start
    ```
    > localhost:8080 admin shipyard

## docker command for real

* container

    1. docker container ls  --- List containers
    1. docker ps --- 查看当前运行的容器
    1. docker ps -a --- 查看所有容器，包括停止的
    1. docker ps -1 --- 查看最新创建的容器，只列出最后创建的
    1. docker ps -n=x --- -n=x, 会列出最后创建的x个容器
    1. docker start docker_run_name/docker_id --- 启动之前已经停止的docker_run_name镜像
    1. docker stop [NAME]/[CONTAINERID] --- 将容器退出
    1. docker kill [NAME]/[CONTAINERID] --- 强制停止一个容器
    1. docker rm [NAME]/[CONTAINERID] --- 不能够删除一个正在运行的容器，会报错。需要先停止容器
    1. docker rm 'docker ps -a -q' --- -a标志列出所有容器，-q标志只列出容器的ID，然后传递给rm命令，依次删除容器(一次性删除所有容器)

    | Name | Meaning |
    | --- | --- |
    | CONTAINER ID | 容器的唯一表示ID |
    | IMAGE | 创建容器时使用的镜像 |
    | COMMAND | 容器最后运行的命令 |
    | CREATED | 创建容器的时间 |
    | STATUS | 容器状态 |
    | PORTS | 对外开放的端口 |
    | NAMES | 容器名 |

* images

    1. docker images --- 使用docker images查看本机上的images
    1. docker search centos ---  搜索合适的images
    1. docker pull [Name] --- 下载images
    1. docker inspect docker.io/centos
    1. docker rmi [Name]/[ID] --- 删除镜像
    1. docker rmi -f [ID] --- 强制删除镜像

    | Name | Meaning |
    | --- | --- |
    | REPOSITORY | 来自于哪个仓库：比如docker.io/centos |
    | TAG | TAG的标记，比如 latest |
    | IMAGE ID | 表示镜像的id号 |
    | CREATED | 创建的时间 |
    | SIZE | 镜像的SIZE |