# uptime

```
~ uptime
17:54:40 up 846 days, 55 min, 10 users,  load average: 0.36, 0.33, 0.48
```

* 这行信息的后半部部分,显示 **load average.  **它的意思是系统的平均负荷.
* 通过里面的三个数字,我们可以从中判断系统负荷是大还是小
* 这3个数字,分别代表1分钟,5分钟,15分钟内系统的平均负荷.
* 当CPU完全空闲的时候,平均负荷为0;当CPU工作量饱和的时候,平均负荷为1\(假设只有一个核\)
* 那么很显然,load average的值越低,比如0.2或者0.3,就说明电脑的工作量越小,系统负荷比较轻



参考文档

http://blog.scoutapp.com/articles/2009/07/31/understanding-load-averages

总结:

假设服务器有16个核.

那么当load average的值小于16的时候,表示现在系统负荷轻.当load average的值大于16就表示负荷过大了.

查看服务器有多少个CPU核心

grep -c 'model name' /proc/cpuinfo



