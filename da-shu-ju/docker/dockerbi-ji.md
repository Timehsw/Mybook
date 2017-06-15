# ubuntu安装docker

## 前提条件

> Docker 要求 Ubuntu 系统的内核版本高于 3.10 ，查看本页面的前提条件来验证你的Ubuntu版本是否支持 Docker 。

打开控制台使用 uname -r命令来查看你当前的内核版本。

\`\`\`

$ uname -r 

 3.11.0-15-generic

\`\`\`

&lt;!-- more --&gt;

\#\# 安装步骤

\`\`\`

sudo apt-get update

sudo apt-get update $ sudo apt-get install wget  //安装wget

wget -qO- https://get.docker.com/ \| sh     //获取最新版本的 Docker 安装包，输入完成之后，就会下载脚本并且安装Docker及依赖包。

docker info //验证安装结果

\`\`\`

\#\# 问题

\#\#\# Cannot connect to the Docker daemon. Is the docker daemon running on this host?

+ 解决:

\`\`\`

sudo su -                       //切换到root

service docker start      //启动docker service

docker images              //显示所有images

docker run hello-world  //重新运行

\`\`\`

恩，是权限问题，当前用户没权限，root用户可以运行



\# 图形化镜像

docker-ubuntu-vnc-desktop

\#\# From Docker Index

docker pull dorowu/ubuntu-desktop-lxde-vnc

\#\# Build yourself

git clone https://github.com/fcwu/docker-ubuntu-vnc-desktop.git

docker build --rm -t dorowu/ubuntu-desktop-lxde-vnc docker-ubuntu-vnc-desktop

\#\# Run

docker run -i -t -p 6080:6080 dorowu/ubuntu-desktop-lxde-vnc

Browse http://127.0.0.1:6080/vnc.html



\# docker 常用命令

\#\# 常用

\|命令\|描述\|

\|---------\|--------\|

\|docker images\|列出所有的镜像\|

\|docker search name\| 搜索docker 容器,name是名字\|

\| docker pull name \|下载容器，name是名字\|

\|docker run -i -t name /bin/bash\|运行name镜像 \|

\|docker exec -i -t name/bin/bash\| 进入容器中\|

\|docker rmi XXXXXX\| 删除一个docker镜像\|

\|docker rm xxxxxx\|删除一个docker容器\|

\|docker ps\|列出正在运行的\(容器\)containers \|

\|docker ps -a\|查看容器状态\|

\|docker commit 3a09b2588478 ubuntu:mynewimage\| 把容器提交为一个镜像保存状态

\#\# 获取 Ubuntu 镜像。

   docker pull ubuntu

完成后执行 docker images 就能看到一个刚刚更新的镜像了。



\#\# 进入容器

   docker run -it ubuntu



\#\# 安装软件、配置环境变量

   首先更新apt-get

   apt-get update 



接下来就可以使用 apt-get install \* 安装你需要的软件了，如果没有就下载安装包自行安装，同时配置好环境变量，这里就不赘述了。



\#\# 启动服务

进入tomcat目录，启动服务，在浏览器打开 0.0.0.0:8080, 如果没有错的话你会看到该服务器无法访问。这是因为我们刚才启动的服务是在docker内，如果不做一些操作的话我们是无法访问到docker内部的服务的。



\#\# 退出容器

所以，我们先退出容器

   exit



\#\# 退出之后执行

   docker ps -a

就能看到我们刚才的容器依然还在，可能大多刚接触docker的人都会犯这个错误，以为退出容器之后容器就销毁了，其实不然。



\#\# 再次进入容器

如果我们想再进入这个容器可以执行下面的命令，容器ID请复制自己的。

   docker exec -it 容器ID bash



\#\# 持久化容器

虽然容器还在运行，但是他并没有持久化，为了防止万一，在我们修改容器里面的内容之后尽快持久化。

   docker commit 容器ID java

这个命令的意思是将我们容器持久化为java镜像。如果镜像不存在就会新建一个。



\#\# 启动这个新建的镜像。

docker run -it -p 8080:8080 java

注意看我们的启动命令发生了变化，多了一个 -P 这个命令的意思是将容器内的 8080 端口暴漏到宿主机上。

再次访问 0.0.0.0:8080，我们就能看到那只小花猫了，真可爱。

刚才那个容器还在占用我们的内存怎么办，干掉他。



\#\# 删除容器

   docker rm 容器ID



至此我们的第一步已经完成了，接下来我们就要集成我们的代码了。



\#\# 集成代码

我们刚才启动的容器是一个完全的独立的黑盒子，它根本不知道我们的代码再哪里，所以我们就要使用docker的挂载卷让宿主机和容器可以共享目录。

不好意思，我们又要干掉刚才启动的那个容器了。

   docker run -it -v /Users/name/web:/opt/root -p 8080:8080 java



我们的启动命令又加入了新成员 -v。这个命令的意思就是将用户根目录下的 web 目录挂在到容器中 /opt/root 目录下。

进入目录后我们就能发现web目录下的文件静静的躺在里面，像是沉睡多年的玛丽苏在等待你的呼唤。



开始呼唤吧。

