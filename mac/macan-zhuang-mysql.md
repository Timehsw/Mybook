# 安装Homebrew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

# 安装brewservices

> 安装这个服务后,我们就可以方便的启动停止用brew安装的相关服务了.比如mysql,redis...

## 安装

```
brew tap homebrew/services
```

## 使用

* 查看服务

```
~ brew services list
Name  Status  User Plist
mysql stopped
redis stopped
```

* 启动服务

  # 启动mysql服务

  ~ brew services start mysql  
    ==&gt; Successfully started `mysql` \(label: homebrew.mxcl.mysql\)

  # 查看服务状态,redis仍然还是停止的

  ~ brew services list  
    Name  Status  User     Plist  
    mysql started hushiwei /Users/hushiwei/Library/LaunchAgents/homebrew.mxcl.mysql.plist  
    redis stopped

* 停止服务

```
brew services stop mysql
```

# 安装MySQL

```
brew info mysql
brew install mysql
```

# 额外配置

```
# 安装brew服务
brew tap homebrew/services
# 启动mysql服务
brew services start mysql 或者 mysql.server start mysql.server stop
# 查看mysql的版本
mysql -V

# 配置mysql的root密码
mysqladmin -u root password 'yourpassword'

mysql -uroot -p
```



