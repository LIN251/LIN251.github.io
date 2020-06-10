---
layout:     post
title:      Centos中Docker的安装和使用
subtitle:   
date:       2020-06-11
author:     Linz
header-img: img/Background/b2.jpg
catalog: true
tags:
    - Linux
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
# service 命令的用法
$ sudo service docker start

# systemctl 命令的用法
$ sudo systemctl start docker
``` 

### 验证安装
``` text
运行程序
$ docker run hello-world
查看版本
$ docker version
查看信息
$ docker info
```

### 查看已有 image 文件
``` text
# 列出本机的所有 image 文件。
$ docker image ls

# 删除 image 文件
$ docker image rm [imageName]
```

### 抓取 image (例：官方仓库)
``` text
$ docker image pull library/hello-world

//官方镜像都在library下面。
//docker image pull 是抓取 image，同github
```


### 查看已有 image 文件
``` text

```

### 查看已有 image 文件
``` text

```


### 查看已有 image 文件
``` text

```

官方文档：https://docs.docker.com/engine/install/centos/