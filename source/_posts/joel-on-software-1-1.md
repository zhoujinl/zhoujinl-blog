---
title: 软件随想录-卷1（上） 
date: 2015-06-20 11:18:18
tags: 随笔
---
joel Spolsky著  杨帆译   
[Gitbook 电子书](https://wizardforcel.gitbooks.io/joel-on-software/content/index.html  "软件随想录")

# 软件开发的五个世界
了解你的世界 
>1.盒装(Shrinkwrap)软件（产品软件）
2.内部用的软件
3.嵌入式软件
4.游戏软件
5.用后即丢的软件

# 二元文化差异   
| 文化类型  | 核心区别 | 区别举例1   | 区别举例1   | 区别举例1   |
| :-------: | :----: | :---: |  :---: |  :---: |
| unix文化 | 重视为程序员提供有用的程序 | 重视命令行 | 一项程序结束如果没有产生任何输出信息，就说明程序执行正确 | 文档应该写的简洁而完整，读者可以推导出未写出的结论并且信任自己的推导，一件事很少会讲两遍.|
| windows文化    | 重视对非程序员提供有用的程序 | 重视图形化界面  | 程序执行后如果没有任何提示你就搞不清楚是因为出错了而没有输出还是没出错只是不输出。| 了解一般使用者一般不读文档，因此一件事情会多次提醒 |

<!-- more -->

# 千万不要做的事情
读代码比写代码还要难
>不要重写代码，不要重写代码，不要重写代码  
因为旧代码里面，包含的某个你看似无用丑陋的代码，可能是前人花很长时间改正过来的BUG。
请在保证单元测试无误的情况下，重构代码，而不是想着重头开始做一套。

# 如何编写技术文档
>1.要幽默，最简单的搞笑方法就是在没有必要写得具体的时候写得具体一点
2.像编写用大脑执行的代码一样编写文档
3.写的尽可能的简单
4.重读并修改几遍
5.尽量不要套用模版

# Unicode和字符集知识 
Unicode实际上只是一个规范，它规定每个字符独一无二的码点。
>在Unicode中，一个字母映射为一个理论概念：码点。至于如何在内存或者硬盘中表示码点，
就是另一件事情了（注:不同编码方式有不同的存储形式）。字母A（U+0645）是一个柏拉图的理想型（platnonic  ideal）。它漂浮在天上，有些抽象。
而字符集编码呢，表示码点的是所谓的编码。例如常见的UTF-8,UTF-16等,都是Unicode家族的编码方式。  
举例：字符串hello的Unicode表示为 U+0048 U+0065 U+006C U+006C U+006F,那么它用UTF-8编码的存储形式为 48 65 6C 6C 6F (注意！) 这和它在ASCII、ANSI以及
其他的所有的OEM字符集中的表示都完全一致，而其他语言（如中文、日文等），则需要几个字节来存储一个码点。

# 乔尔测试
> 1.你们使用版本控制系统吗？
2.有一键部署吗？
3.有每日构建吗？
4.有Bug数据库吗？
5.你们是否在写新代码前保证Bug都修复完了？
6.有最新的开发计划吗？
7.有需求文档吗？
8.程序员们有安静的工作环境吗？
9.你们使用能买到的最好的工具吗？
10.有测试团队吗？
11.应聘者在面试时写代码吗？
12.你们进行目标用户随机可用性测试吗？



# 轻松掌握软件开发进度
>1.使用excel
2.保持简单
3.每个功能点应该分成几个子任务
4.只有程序员才能准确的预估时间
5.细分任务，每个任务以小时为单位。
6.记录原始和当前的时间估计，训练自己的时间估计准度。
7.每天更新实际用时。
8.把休假考虑在内
9.把调试代码的时间也考虑在内
10.把集成时间考虑在内
11.预留缓冲时间
12.不要压缩程序员的预估时间
13.缩减功能以减少开发时间

# 干扰射击  
>微软频繁推出的历代数据库连接技术（ODBC,RDO,DAO,ADO,OLEDB,ADO.NET...），目的火力压制，迫使竞争者们用尽全部精力来跟上未然的节拍，移植现有的功能，从而没有时间研发新功能。因此必须抓紧时间，把开发的主动权掌握在自己的手里，二是必须每天进步。

# 修复bug
* 尽可能收集bug的所有信息
* 衡量bug的成本与收益
* 算出修复所有bug的价值  
   
# 错误报告
* 建立bug数据库(小项目可以用记事本)
* 每个好的错误报告都要包括以下三个步骤：
1.重现的步骤
2.期望看到的  
3.实际看到的
好的测试员会把重现的步骤缩减到最短。只有一开始测出问题的人才能关闭这个bug。
要解决错误可以有很多种办法，解决理由有：不予修正，暂缓，无法重现，重复的问题，设计限制。
