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