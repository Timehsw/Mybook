

# 切换root账号

```
macbook pro启用root的方法
用管理员帐号进入shell:
　　1) sudo passwd root
　　2) 输入新的root密码。
　　3) su
　　4) 使用新密码
　　这样就进入到root帐号了
```

# 添加安装任何来源的文件

安装破解软件的时候,需要设置成-允许从任何来源,不然会出现

xxx.app已损坏,打不开.你应该将它移到废纸篓

```
sudo spctl --master-disable
```

# 安装brew包管理器

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
#更新 brew
brew update
```

# brew安装 python

Python会被安装到/usr/local/bin目录下

```
brew install python
# 然后安装 ipython
sudo pip install ipython
```

# brew 安装 wget

```
brew install wget
```

# brew安装 node

```
brew install node
```

# npm安装hexo

* 下载

```
npm install -g hexo-cli
```

* 验证

```
输入 hexo 有提示就成了
```

# 配置 GitHub免密

```
重新打开bash，输入：
ssh-keygen -t rsa -C "Github的注册邮箱地址"
一路Enter过来就好，得到信息：
Your public key has been saved in /Users/hushiwei/.ssh
找到该文件，打开（sublime text），Ctrl + a复制里面的所有内容，然后进入Sign in to GitHub：
New SSH key ——Title：blog —— Key：输入刚才复制的—— Add SSH key
```

# 源码方式安装pip\(如果重新用 brew 安装了 python,那么 pip 已经安装了\)

```
wget https://bootstrap.pypa.io/get-pip.py
sudo python get-pip.py
```



# 安装jdk

* 配置scala,maven,环境变量

* maven和Scala

```
.tgz
解压：tar zxvf FileName.tgz
压缩：tar zcvf FileName.tgz FileName
```

* 环境变量

    hushiweideMacBook-Pro:Downloads hushiwei$ more .bash_profile 
    alias ll='ls -lF'
    alias ll='ls -alF'
    JAVA_HOME=`/usr/libexec/java_home`
    SCALA_HOME=/Users/hushiwei/devApps/scala-2.10.5
    MAVEN_HOME=/Users/hushiwei/devApps/maven-3.3.9
    CLASSPAHT=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
    PATH=$SCALA_HOME/bin:$MAVEN_HOME/bin:$JAVA_HOME/bin:$PATH:/usr/local/bin:

安装MySQL

* 下载

\[下载地址\]\(https://dev.mysql.com/downloads/mysql/\)

# brew的安装OSX最好用的免费播放器

## 参考

[https://codesky.me/archives/mpv-config.wind](https://codesky.me/archives/mpv-config.wind)

## 安装

```
brew tap mpv-player/mpv
brew install mpv
brew linkapps mpv
```

## 说明

执行上面的命令后,就安装完成

