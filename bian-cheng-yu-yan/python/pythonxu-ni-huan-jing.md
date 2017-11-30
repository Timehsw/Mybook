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



