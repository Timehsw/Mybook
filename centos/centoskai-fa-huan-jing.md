#  安装gcc

```
yum -y install gcc gcc-c++ kernel-devel
```

# 源码方式安装python2.7

```
wget https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz
tar xf Python-2.7.8.tgz
cd Python-2.7.8
./configure --prefix=/usr/local
make && make install
```

# 安装pip

```
首先安装epel扩展源：
sudo yum -y install epel-release
sudo yum upgrade python-setuptools
sudo yum install gcc libffi-devel python-devel python-pip python-wheel openssl-devel libsasl2-devel openldap-devel
```



