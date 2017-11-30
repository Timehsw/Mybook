我的电脑是macbookpro.我在电脑里面分别装了python2.7和python3.6.

当我用pip安装了virtual后,我如果想要对应版本的python

# virtualenv的参数

```
hushiwei@hsw  ~/virtual  virtualenv
You must provide a DEST_DIR
Usage: virtualenv [OPTIONS] DEST_DIR

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -v, --verbose         Increase verbosity.
  -q, --quiet           Decrease verbosity.
  -p PYTHON_EXE, --python=PYTHON_EXE
                        The Python interpreter to use, e.g.,
                        --python=python2.5 will use the python2.5 interpreter
                        to create the new environment.  The default is the
                        interpreter that virtualenv was installed with
                        (/usr/local/opt/python3/bin/python3.6)
  --clear               Clear out the non-root install and start from scratch.
  --no-site-packages    DEPRECATED. Retained only for backward compatibility.
                        Not having access to global site-packages is now the
                        default behavior.
  --system-site-packages
                        Give the virtual environment access to the global
                        site-packages.
  --always-copy         Always copy files rather than symlinking.
  --unzip-setuptools    Unzip Setuptools when installing it.
  --relocatable         Make an EXISTING virtualenv environment relocatable.
                        This fixes up scripts and makes all .pth files
                        relative.
  --no-setuptools       Do not install setuptools in the new virtualenv.
  --no-pip              Do not install pip in the new virtualenv.
  --no-wheel            Do not install wheel in the new virtualenv.
  --extra-search-dir=DIR
                        Directory to look for setuptools/pip distributions in.
                        This option can be used multiple times.
  --download            Download preinstalled packages from PyPI.
  --no-download, --never-download
                        Do not download preinstalled packages from PyPI.
  --prompt=PROMPT       Provides an alternative prompt prefix for this
                        environment.
  --setuptools          DEPRECATED. Retained only for backward compatibility.
                        This option has no effect.
  --distribute          DEPRECATED. Retained only for backward compatibility.
                        This option has no effect.
```

可以看到里面的--python参数可以指定虚拟环境的python版本.并且说明了默认是python3.6

# 创建虚拟环境

## virtual安装Python2.7

```
virtualenv --python=python python2env
```

## virtual安装Python3.6环境

```
virtualenv --python=python3 python3env
```

# 激活进入虚拟环境

```
source python2env/bin/activate
source python3env/bin/activate
```

# 退出虚拟环境

```
deactivate
```

# 删除虚拟环境

```
# 直接用rm删除目录就是删除虚拟环境了
rm -rf 虚拟环境的目录名称
```

# 激活虚拟环境,将全部依赖写入文件

```
pip freeze > requirements.txt
```

进入项目内,安装全部依赖

```
pip install -r requirements.txt
```

## virtualenvwrapper

> virtualenvwrapper是virtualenv的扩展管理包，用于更方便管理虚拟环境.

他可以做;

1. 将所有虚拟环境整合在一个目录下
2. 管理（新增，删除，复制）虚拟环境
3. 切换虚拟环境

## 安装

```
pip install virtualenvwrapper
```

## 使用方法

1.初始化配置

默认virtualenvwrapper安装在/usr/local/bin下面，实际上需要运行virtualenvwrapper.sh文件才行；

所以需要先进行配置一下：

1.1 创建虚拟环境管理目录:

```
mkdir $HOME/.local/virtualenvs
```

1.2 在~/.bash\_profile中添加行

```

export VIRTUALENV_USE_DISTRIBUTE=1        #  总是使用 pip/distribute
export WORKON_HOME=$HOME/.local/virtualenvs       # 所有虚拟环境存储的目录
if [ -e $HOME/.local/bin/virtualenvwrapper.sh ];then
    source $HOME/.local/bin/virtualenvwrapper.sh
else if [ -e /usr/local/bin/virtualenvwrapper.sh ];then
    source /usr/local/bin/virtualenvwrapper.sh
fi
  fi
export PIP_VIRTUALENV_BASE=$WORKON_HOME
export PIP_RESPECT_VIRTUALENV=true
```

2.使用方法

所有的命令可使用：`virtualenvwrapper --help` 进行查看，这里列出几个常用的：

* 创建基本环境：mkvirtualenv \[环境名\]

* 删除环境：rmvirtualenv \[环境名\]

* 激活环境：workon \[环境名\]

* 退出环境：deactivate

* 列出所有环境：workon 或者 lsvirtualenv -b





