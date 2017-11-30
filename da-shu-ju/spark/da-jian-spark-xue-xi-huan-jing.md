# 安装spark

我在官网下载最新的spark2.2.0

https://spark.apache.org/downloads.html

```
 hushiwei@hsw  ~/bigdataframe  pwd
/Users/hushiwei/bigdataframe
# 解压缩
 tar zxvf spark-2.2.0-bin-hadoop2.7.tgz -C ~/bigdataframe
# 配置SPARK_HOME
vim ~/.bash_profile
SPARK_HOME=/Users/hushiwei/bigdataframe/spark-2.2.0-bin-hadoop2.7 
```

现在可以去检查Spark安装,去Spark文件夹并执行pyspark

    hushiwei@hsw  ~/bigdataframe  cd spark-2.2.0-bin-hadoop2.7

    hushiwei@hsw  ~/bigdataframe/spark-2.2.0-bin-hadoop2.7  bin/pyspark
    Python 2.7.13 (default, Apr  4 2017, 08:47:57)
    [GCC 4.2.1 Compatible Apple LLVM 8.1.0 (clang-802.0.38)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
    Setting default log level to "WARN".
    To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
    17/11/30 09:50:44 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
    17/11/30 09:50:49 WARN ObjectStore: Version information not found in metastore. hive.metastore.schema.verification is not enabled so recording the schema version 1.2.0
    17/11/30 09:50:49 WARN ObjectStore: Failed to get database default, returning NoSuchObjectException
    17/11/30 09:50:50 WARN ObjectStore: Failed to get database global_temp, returning NoSuchObjectException
    Welcome to
          ____              __
         / __/__  ___ _____/ /__
        _\ \/ _ \/ _ `/ __/  '_/
       /__ / .__/\_,_/_/ /_/\_\   version 2.2.0
          /_/

    Using Python version 2.7.13 (default, Apr  4 2017 08:47:57)
    SparkSession available as 'spark'.
    >>> exit()

如果一切正常安装,可以看到类型于上的输出.

但是,目前为止,你可能会在Spark初始化时看到此警告

```
WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
```

要解决此问题,必须安装hadoop.这是可选的,因为Spark可以运行.但是我猜测使用Hadoop可能会有某些性能改进

# 安装hadoop

我在官网上下载的是hadoop2.7.4

http://hadoop.apache.org/releases.html

```

```



