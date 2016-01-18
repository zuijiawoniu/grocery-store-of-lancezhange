# shell

[Bash 快捷键大全](https://linux.cn/article-5660-weibo.html)

tldr 可以展示常用命令的常见用法


管道（参考[管道与Unix哲学](http://bindog.github.io/blog/2014/09/25/pipes-and-filters/)）


一些细节要注意，例如， `uniq` 只是去除**连续的重复行**，可以认为是局部去重，所以并不能用在完全去重的场景中(除非先对数据做排序)

### awk 和 sed

[SED & AWK](http://dongweiming.github.io/sed_and_awk/?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io#/) by 董伟明


### 系统监控
常用如下十个命令（参见[Linux Performance Analysis in 60,000 Milliseconds by NetFlix](http://techblog.netflix.com/2015/11/linux-performance-analysis-in-60s.html)）

uptime
dmesg | tail
vmstat 1
mpstat -P ALL 1
pidstat 1
iostat -xz 1
free -m
sar -n DEV 1
sar -n TCP,ETCP 1
top





