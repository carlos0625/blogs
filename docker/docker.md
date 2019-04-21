# Ubuntu 18.04 LTS 安装 Docker CE

  本篇博客参考Docker官网，采用配置Repository方式在Ubuntu 18.04 LTS下安装[Docker CE](https://docs.docker.com/)

## 添加Repository

* **更新软件源**

```shell
$ sudo apt-get update
```

* **安装镜像允许apt使用基于HTTPS的repository**

```shell
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

* **添加Docker官方GPG密钥(使用中科大软件源)**

```shell
$ curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
```

* **设置Docker版本为稳定版(使用中科大软件源)**

```bash
$ sudo add-apt-repository \
"deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu \
$(lsb_release -cs) \
stable"
```

## 安装Docker CE

```shell
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

## 验证安装成功与否

```shell
$ sudo docker run hello-world
```

## 将当前用户添加到docker用户组避免使用`sudo`命令

```shell
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
$ reboot
```

## 设置docker为开机启动

```shell
$ sudo systemctl enable docker.service
```

## 配置加速器加速下载镜像的速度

```shell
$ curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://f1361db2.m.daocloud.io
```