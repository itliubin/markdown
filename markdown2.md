# 代码块
## 行内代码

这是一个bash 的脚本  `datetime=date +%Y%m%d`使用反引号包围代码 

## 代码块的使用
```bash
#!/bin/bash
#disk used altert sendmail 
host='192.168.56.34'
email_logfile='/root/diskdetail.txt'
email_logfilenow='/root/diskdetail.now'
for d in `df -P | grep /dev | awk '{print $5}' | sed 's/%//g'`
do 
   if [ $d -gt 10 ];then
     echo `date`>>$email_logfile;
     echo `date`>$email_logfilenow;
     df -h >>$email_logfile;
     df -h >$email_logfilenow
     echo "$host 磁盘利用率超过10%" | mail -s "$host 磁盘利用率告警" -a $email_logfilenow liubin@zoneyet.com 
     exit 0
   fi
done
```
使用3个反引号对代码进行包围，开使的3个反引号后面跟上代码的编写语言，这样可以有语法高亮提示


# 引用
> 这是一个引用

>>> 这是多重引用

貌似引用在实际过程中用的不多

# 这是超链接 

## 外部的连接 [点击连接的文字](连接的url)
[百度](http://wwww.baidu.com)

## 内部的连接
+ 链接到同一个目录下的其他文件  
[ 段落、标题、序列、加粗、斜体的写法](markdown.md)
+ 连接到本文档的某个标题
[代码块](markdown2.md#代码块)

# 这是图片部分
![本地图片](weixin.jpg)  
![网络图片](http://img0.bdstatic.com/static/searchdetail/img/logo-2X_0c4ef02.png)



<!--当一个文字做多次超连接的时候，可以使用引用的方式如下 -->

# 对一个文字需要做多次出现，都需要链接的情况

[baidu]




[baidu]: http://www.baidu.com

