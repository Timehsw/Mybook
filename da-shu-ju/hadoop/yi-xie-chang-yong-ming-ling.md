# 查看日志

当执行完一个mapreduce后,到yarn里面去看日志,说实话不是很方便.我们可以直接找到日志目录,然后查看日志

把这个mapreduce的appid替换即可.

```
hadoop fs -text /tmp/logs/root/logs/application_1490332937897_68109/*
```

# 合并小文件到本地

有时候,我们执行完mapreduce后,生成了好多小文件.我们需要把文件合并拿到本地的时候,可以执行这个命令

```
 hadoop fs -getmerge hdfspath localpath
 eg:
 hadoop fs -getmerge /user/hsw/outputt mergeapp
```



