# 命令

实时监控日志：``` tail -f filename ```

实时监控10行日志信息 ```tail -10f filename```

查看日志尾部的最后100行日志信息：```tail -n 100 filename```

查看日志100行之后的日志信息：```tail -n +100 filename ```

查看文本开始的头100行信息：```head -n 100 filename```

查看文本最后100行信息以上的内容 ```head -n -100 filename```

查看文本文件100-120行之间的内容 ```cat -n filename |tail -n +100|head -n 20 ```    

从文本的尾部往头部展现日志内容 ```tac filename```

在多个文件中查 ```grep "match_pattern" file_1 file_2 file_3 ...```

输出除之外的所有行 -v 选项：```grep -v "match_pattern" file_name```

统计文件或者文本中包含匹配字符串的行数 -c 选项：```grep -c "text" file_name```

输出包含匹配字符串的行数 -n 选项：```grep "text" -n file_name```

查看2019-08-06 22点这一个小时以内的日志信息: ``` grep '2019-08-06 22' filename```

只打印文件的第一行内容 ```sed -n '1p'  filename```

查看文件的第一行到第十行之间的内容 ```sed -n '1,10p' filename```

查看2019-08-06 22:43-22:44之间的日志记录：```sed -n '/2019-08-06 22:43/,/2019-08-06 22:44/p' filename```

日志的第1-20行内容：``` nl log.file | sed -n '1,10p'```

每一页展示10条数据信息：```more -10 filename```

简单统计一份日志里面出现‘test’关键字的行数: ```grep 'test' ./log.file |wc -l```

以上摘自: https://zhuanlan.zhihu.com/p/77608977


日志内容特别多，打印在屏幕上不方便查看

其他:

(1)使用more和less命令,

       如： cat -n test.log |grep "debug" |more     这样就分页打印了,通过点击空格键翻页

(2)使用 >xxx.txt 将其保存到文件中,到时可以拉下这个文件分析

        如：cat -n test.log |grep "debug"  >debug.txt

摘自: https://hacpai.com/article/1567662754560
