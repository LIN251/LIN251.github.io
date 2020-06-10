---
layout:     post
title:      Centos中Docker的安装和使用(待续)
subtitle:   
date:       2020-06-11
author:     Linz
header-img: img/Background/b2.jpg
catalog: true
tags:
    - Centos
---


### 卸载旧版本Docker

``` text
$ sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
``` 


### 设置仓库
``` text
$ sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```

### 设置稳定的仓库

``` text
$ sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```


### 安装 Docker Engine-Community

``` text
$ sudo yum install docker-ce docker-ce-cli containerd.io
``` 

### 启动 Docker
``` text
// service 命令的用法
$ sudo service docker start

// systemctl 命令的用法
$ sudo systemctl start docker
``` 

### 验证安装
``` text
// 运行程序
$ docker run hello-world
// 查看版本
$ docker version
// 查看信息
$ docker info
```

### 查看已有 image 文件
``` text
// 列出本机的所有 image 文件。
$ docker image ls

// 删除 image 文件
$ docker image rm [imageName]
```

### 抓取 image (例：官方仓库)
``` text
// 官方镜像都在library下面。
// docker image pull 是抓取 image.
$ docker image pull library/hello-world
```


### 执行 image
``` text
//两种方法。docker container run 命令具有自动抓取 image 文件的功能。如果发现本地没有指定的 image 文件，就会从仓库自动抓取。
$ docker container run hello-world
$ docker run hello-world

```

### 终止执行中的container
``` text
//一些container是不会停止的，所以需要手动停止
$ docker container kill [containID]
```


### 查看已有 image 文件
``` text

```

官方文档：https://docs.docker.com/engine/install/centos/