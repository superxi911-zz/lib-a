# 部署 nginx

nginx 镜像的日常使用非常频繁。下面介绍如何快速部署 nginx 应用到 CLaaS 平台:

- [镜像准备](#1)
- [部署应用](#2)
- [查看应用](#3)

## a 镜像准备
CLaaS 平台提供了[镜像仓库](../image/README.md)的功能，用户可以非常方便的管理自己的镜像。因为内部镜像仓库有很多版本的 nginx 镜像，这里直接搜索一个 nginx 镜像来部署。点击图上红色框中的按钮部署。

![PNG](../images/getstarted-nginx-image.png)

## 部署 b 应用
填写应用的基本信息，实例数是应用运行在 kubernetes 中 pod 数量。

![PNG](../images/getstarted-basic-info.png)

选择部署位置, Kubernetes 使用分区来隔离应用，下面把 nginx 部署在 1 分区。

![PNG](../images/getstarted-deploy-place.png)

填写容器信息，为容器选择资源配额，可以使用[数据卷](../storage/README.md)挂载到容器。这样即使应用删除了数据也会一直保存着。容器端口填写 80，因为 nginx 会暴露 80 端口。

![PNG](../images/getstarted-contain-info.png)

填写服务信息，让 nginx 对外映射一个端口。如果是一个数据库服务比如 mongo，只需要内部访问可以选择`只限集群内部访问`，这里选择对外暴露端口用于在浏览器上直接查看 nginx 主页。

![PNG](../images/getstarted-service-info.png)

## 查看应用

到这里应用就已经部署完了，可以在应用详情查看应用的监控，日志等信息。在[应用](../app/README.md)中会详细解释这些功能，等待几秒钟创建容器，状态变为绿色那么应用就成功运行了：

![PNG](../images/getstarted-app.png)

这里可以直接通过上图的应用地址访问 nignx 主页。

![PNG](../images/getstarted-nginx.png)
