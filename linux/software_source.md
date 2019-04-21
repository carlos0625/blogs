# Ubuntu下的国内软件源

## 阿里云

  Ubuntu 18.04 (bionic)

```properties
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
#deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
#deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
#deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
#deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse

#deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
#deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
```

## 清华大学

```properties
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse

deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse

deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse

deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

## 中科大

```properties
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
#deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse

deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
#deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse

deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
#deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse

deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
#deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse

#deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
#deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

## 163

```properties
deb http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
#deb-src http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
#deb-src http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
#deb-src http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse

deb http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
#deb-src http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse

#deb http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
#deb-src http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
```

## Ubuntu 版本号

Number | Name
-- | --
14.04 LTS | Trusty
14.10 LTS | Utopic
15.04 | Vilid
15.10 | Wily
16.04 LTS | Xenial
16.10 | Yakkety
17.04 LTS | Zesty
17.10 | Artful
18.04 LTS | Bionic
18.10 | Cosmic
19.04 | Disco

## 切换软件源

  Ubuntu下的`/etc/apt/sources.list`文件就是软件源文件之一，我们只需对其进行修改，而修改之前，为了以防万一先做一下备份。

  ```bash
  # 备份
  $ sudo mv /etc/apt/sources.list /etc/apt/sources.list.backup
  # 修改源
  $ sudo vim /etc/apt/sources.list
  ```

  进入vim编辑器后，我们将所有内容注释或者清空，然后将上述的4大源的任意一个复制粘贴到该文件，保存并退出，然后进行更新源：

  ```bash
  $ sudo apt-get update
  ```

  至于哪一个速度快，我也不知道，一般来说阿里云的软件源是最快的。
