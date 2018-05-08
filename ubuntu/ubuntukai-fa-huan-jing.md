# 给系统更新

```
sudo apt-get update
```

# 安装sublime3

* 1.在商店里下载sublime3后
* 2.用第一个这个就可以注册成功

```
—– BEGIN LICENSE —–
eldon
Single User License
EA7E-1122628
C0360740 20724B8A 30420C09 6D7E046F
3F5D5FBB 17EF95DA 2BA7BB27 CCB14947
27A316BE 8BCF4BC0 252FB8FF FD97DF71
B11A1DA9 F7119CA0 31984BB9 7D71700C
2C728BF8 B952E5F5 B941FF64 6D7979DA
B8EB32F8 8D415F8E F16FE657 A35381CC
290E2905 96E81236 63D2B06D E5F01A69
84174B79 7C467714 641A9013 94CA7162

—— END LICENSE ——



Ryan Clark
Single User License
EA7E-812479
2158A7DE B690A7A3 8EC04710 006A5EEB
34E77CA3 9C82C81F 0DB6371B 79704E6F
93F36655 B031503A 03257CCC 01B20F60
D304FA8D B1B4F0AF 8A76C7BA 0FA94D55
56D46BCE 5237A341 CD837F30 4D60772D
349B1179 A996F826 90CDB73C 24D41245
FD032C30 AD5E7241 4EAA66ED 167D91FB
55896B16 EA125C81 F550AF6B A6820916

Michael Barnes
Single User License
EA7E-821385
8A353C41 872A0D5C DF9B2950 AFF6F667
C458EA6D 8EA3C286 98D1D650 131A97AB
AA919AEC EF20E143 B361B1E7 4C8B7F04
B085E65E 2F5F5360 8489D422 FB8FC1AA
93F6323C FD7F7544 3F39C318 D95E6480
FCCC7561 8A4A1741 68FA4223 ADCEDE07
200C25BE DBBC4855 C4CFB774 C5EC138C
0FEC1CEF D9DCECEC D3A5DAD1 01316C36
```

* 3.安装插件包管理

```
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

# 安装java,scala,mvn,intellij idea

* 1.解压tar包
* 2.设置环境变量
* 3.加载环境变量以生效

# 安装Mysql

> ubuntu上安装MySQL非常简单只需要几条命令就可以完成。

```
　　1. sudo apt-get install mysql-server

　　2. apt-get isntall mysql-client

　　3. sudo apt-get install libmysqlclient-dev
```

安装过程中会提示设置密码什么的，注意设置了不要忘了，安装完成之后可以使用如下命令来检查是否安装成功：

```
sudo netstat -tap | grep mysql
```

通过上述命令检查之后，如果看到有mysql 的socket处于 listen 状态则表示安装成功。

登陆mysql数据库可以通过如下命令：

```
mysql -u root -p
# -u 表示选择登陆的用户名， -p 表示登陆的用户密码，上面命令输入之后会提示输入密码，此时输入密码就可以登录到mysql。
```

# 安装 python,pip 环境

```
sudo apt-get install python-pip python-dev
sudo pip install --upgrade pip
```

pip安装常用模块

```
sudo pip install django
sudo pip install MySQL-python
sudo pip install beautifulsoup4
```

# 安装git

```
sudo apt-get install git
```

git的执行文件在/usr/bin/git

# 安装nodejs及npm

```
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install python-software-properties python g++ make nodejs npm
```

# 安装jekyll步骤

> 安装一个本地的jekyll环境，方便写博客的时候调试预览效果

```
sudo apt-get install ruby
sudo apt-get install ruby-dev(用这个命令，不然后面装jekyll会出现缺文件的错误)
ruby -v （检查一下版本）
gem -v （检查一下版本）
sudo apt-get install nodejs （把nodejs也装上）
sudo gem install jekyll （最后可以安装jekyll了）
```

**注意:**   最后安装jekyll的时候，如果报了缺少什么的错误。根据提示的错误，下载缺少的文件即可。

