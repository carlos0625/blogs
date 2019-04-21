# Linux虚拟机上安装KVM

## 前言

  本文虚拟机安装[Ubuntu 18.04 LST](https://www.ubuntu.com/download/desktop/thank-you?country=CN&version=18.04.2&architecture=amd64)，KVM为Ubuntu 14.04

  如何安装虚拟机，请自行百度或谷歌。要求虚拟机的配置为：

  * 4个VCPU

  * 2GB的内存

  * 50GB虚拟磁盘(重新编译内核需要70G以上)

  * 开启Virtualize Intel VT-x/EPT and AMD-V/RV 和 Virtual CPU performance counters

## 安装步骤

### Ubuntu 18.04 LTS软件源切换成清华大学软件源

* **备份当前的软件源文件**

```shell
$ sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
```

* **使用编辑器编辑source.list**

```shell
$ sudo vim /etc/apt/sources.list
```

  内容如下：

```properties
deb https://mirrors.tuna.tsinghua.edu.cn/ bionic main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse

# 下面为预发布软件源，不建议使用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

### 安装libguestfs-tools

```shell
$ sudo apt-get update
$ sudo apt-get insatll qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils \
libosinfo-bin libguestfs-tools virt-top virtinst
```

### 在虚拟机Ubuntu 18.04 LTS上安装KVM

```shell
$ virt-install \
--name guest0 \
--virt-type=kvm \
--ram 1024 \
--disk path=guest0.img,size=25 \
--vcpus 2 \
--os-type linux \
--graphics none \
--console pty,target_type=serial \
--location 'http://mirrors.aliyun.com/ubuntu/dists/trusty/main/installer-amd64/' \
--extra-args 'console=ttyS0,115200n8 serial'
```

### 配置串口

  修改`/etc/default/grub`

  ```bash
  ……
  GRUB_CMDLINE_LINUX="console=ttyS0,115200n8"
  ……
  ```

## 常用管理kvm命令

* **开启客户端**

```shell
$ virsh start guest0
```

* **连接kvm串口**

```shell
$ virsh console guest0
```

* **从KVM终端退出**

```shell
键盘 ctrl + ]
```

* **关闭kvm**

```shell
$ virsh shutdown guest0
```

* **查看当前运行的kvm**

```shell
$ virsh list
```

* **强制杀死KVM**

```shell
$ virsh destroy guest0
```