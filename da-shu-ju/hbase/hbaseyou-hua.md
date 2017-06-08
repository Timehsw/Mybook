# 用HFile直接入库

无论是一条put,还是批量put,当数据量很大的时候,都会对region server造成很大的请求压力.

因此我们可以选择直接生成hbase存储在hdfs上的底层数据格式hfile.然后用bulkload直接导入到hbase中.这样可以减少hbase的请求压力.

# 问题

我在运行当中,似乎看到了会去读取hbase有多少个region.

那么问题来了,生成的hfile可以复制到多张hbase表中吗



