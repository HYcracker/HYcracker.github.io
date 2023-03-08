<font size=6>Linux命令篇 linux命令大全简洁明了 linux学习笔记</font>

![在这里插入图片描述](https://img-blog.csdnimg.cn/424ac383440d4a3586799a0ad4ca349f.png)

# Linux 命令大全
@[toc]

# 一、  常用的基础命令

## 查看目录：

	01.   ls (list) 查看当前文件夹下的内容

	02.   pwd (print work directory) 查看当前所在文件夹

## 	切换目录：

	03.   cd [目录名] (change directory) 切换文件夹
  
  
  
  
  

## 	创建和删除：
	04.   touch [文件名] (touch) 如果文件不存在则新建文件

	05.   Mkdir [目录名] (make directory) 创建目录

	06.   rm [文件名] (remove) 删除指定文件

## 	拷贝和移动文件：

	07.   cp

	08.   mv

##	查看文件内容：

	09.   cat 

	10.   more

	11.   grep

## 	其他：

	12.   clear 清屏

	13.   echo

	14.   重定向 > 和 >>

	15.   管道 |

## 	小技巧

	Ctrl + shift + = 放大终端窗口的字体显示

	Ctrl + - 缩小终端窗口的字体显示

	 

##	终端命令格式

Command [-options] [parameter] （[ ]代表可选）

说明：

        · command ：命令名，相应功能的英文单词或者缩写

        · [-options] ：选项，可用来对命令进行控制，也可以省略

        · [parameter] ：参数，可以是零个，也可以是多个

 

##             1.1 ls的常用选项

  ##         参数：

             -a 显示指定目录下的所有子目录与文件，包括隐藏文件

             -l 以列表的方式显示文件的详细信息

             -h 配合-l使用

##         通配符：

             * 代表任意个数的字符

             ？代表任意一个字符

             [ ] 表示可以匹配字符组中的任意一个

             [abc] 匹配a、b、c中的任意一个

             [a-f] 匹配从a到f范围内的任意一个字符

 

##             02.目录切换操作

             2.1 cd

             cd 切换到当前用户的主目录（/home/用户目录）

             cd ~ 切换到当前用户的主目录（/home/用户目录）

             cd . 保持在当前目录不变

             cd .. 切换到上级目录

             cd – 在最近两次工作的目录之间切换

 

 ##            03．创建和删除操作

 ###          3.1  touch

           创建文件或修改文件日期

             ·| 如果文件不存在，则可以创建文件

             ·| 如果文件已经存在，则可以修改文件的末次修改日期

 

###             3.2  mkdir

           创建一个新的目录

             参数：-p 可以速归创建目录（同一根目录内创建多个目录）

             |     新建目录的名称 不能与当前目录中 已有的目录或文件 同名

 

##             3.3  rm

             · 删除文件或目录

             | 使用rm命令必须谨慎，因为文件删除后不能恢复

             **参数：**
             -f 强制删除，忽略不存在的文件

             -r 速归地删除目录下的内容，删除文件夹时必须加此参数

             

 ##            4.0 移动和拷贝文件

##           4.1  tree

          tree [目录] 以树状图的形式列出文件目录结构

 

             4.2 cp（copy）

              cp 源文件 目标文件  复制文件或目录

        选项：

             -i 覆盖文件前提示

             -r 若给出的源文件是目录文件，则cp

                    将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名

 

##             4.3 mv（move）

             mv 源文件 目标文件  可以用来移动 文件或目录，也可以给文件或目录重命名

             选项：-i 覆盖文件前提示

             

 

 ##            5.0 目录文件类

##          5.1  cat

             cat (concatenate) 查看文件内容、创建文件、文件合并、追加文件内容等

                                         该命令会显示文件所有内容，适合内容较少的文本文件

             选项

             -b 对非空输出行编号

             -n 对所有输出行编号

       结尾带 | more 可以进行管道命令more，与cat内内容进行交互

 

 ##            5.2  more

           more 用于分屏显示文件内容，每次只显示一页内容

                      适用于内容较多的文件

             适用于more命令的操作

             

 

##             5.3  less

           less指令用于分屏查看文件内容，其功能与more类似但是更加强大。对于显示大型文件具有更高效率。

             基本语法： less 要查看的文件

             快捷键： 

       

 

 

##             5.4  echo

             Echo输出内容到控制台

             基本语法： echo [选项] [输出内容]

             

 

##           5.5  head

             head用于显示文件开头部分内容，默认情况下head指令显示文件前10行内容

             基本语法： 

             head 文件
             head -n 5 文件 （查看文件开头的前5行内容）

 

##             5.6  tail

             tail用于输出文件中尾部的内容，默认情况下tail指令显示文件的后10行内容

             基本语法：

             tail 文件

             tail -n 5 文件  （查看文件尾5行的内容）

             tail -f 文件 （实时追踪该文档的所有更新）

 

             

             

 

##	5.7  >指令和 >>指令

             >为输出重定向（会全部原文件进行覆盖） >>为追加（不会覆盖）

             基本语法：

             ls -lh >文件 (列表的内容覆盖写入文件中,文件不存在则自动创建。同样用于tree指令)

             ls -al >>文件 （列表的内容追加到文件的末尾）

             cat 文件1 > 文件2 （将文件1的内容覆盖到文件2）

             echo “内容”>> 文件

 

##	5.8  ln

	ln  创建软链接（类似win系统下的快捷方式）

	基本语法：

	ln -s [原文件或目录] [软链接名] （如: ln -s /root /home/myroot 给root文件夹创建/home目录下名为myroot的软链接）   

	当时用pwd指令查看目录时，仍显示软链接所在目录

	 

##	5.9  history

	查看已经执行过的历史命令，也可以执行历史指令

	基本语法：

	history 10 (显示最近使用过的10条指令)

	!5 (执行历史序号为5的指令)

	 

	 

	 

##	6.0  运行级别

##	0：关机

	1：单用户状态

	2：多用户状态无网络服务

	3：多用户状态有网络服务

	4：系统未使用，保留给用户

	5：图形界面，即桌面

	6：系统重启

	基本语法：

	Init [0 1 2 3 4 5 6] 以init来切换运行级别

	systemctl get-default 显示默认运行级别

	systemctl set-default TARGET.target 设置默认运行级别

	如：systemctl set-default multi-user.target 设置默认运行级别为3

	   systemctl set-default graphical.target 设置默认运行级别为5

	 

	 

## 	7.0  关机、重启

	基本语法：

	shutdown -h now 立刻关机

	shutdown -h 1    1分钟后关机

	Shutdown -r now 立刻重启

	halt                关机

	reboot             重启

	sync               把内存的数据同步到磁盘

	关机和重启的指令会在关机前自动执行一次 sync 命令

##	8.0  用户登录和注销

	使用su - root 可以切换为root用户

	logout 登出或返回上一级用户(在图形运行级别下无效)

##	9.0  时间日期

##	9.1  显示日期

	date      显示当前时间

	date +%Y  显示当前年份

	date +%m 显示当前月份

	date +%d  显示当前天

	date “+%Y-%m-%d %H:%M%S” 显示年月日时分秒

	cal       查看日历(当月)

	cal 2021  查看全年日历

	可以自由组合来显示想要的内容

##	9.2  设置日期

	date -s 字符串时间 (date -s “2020-11-03 20:02:10”)

	 

	 

##	10.0  搜索查找类

###	10.1  find

	find指令将从指定目录向下递归地遍历其各子目录，讲满足条件的文件或目录显示在终端

	**基本语法：**

	find [搜索范围] [选项]

	

	（-size +n大于 -n小于 n等于 单位:k M G 区分大小写）

	如：find /home -name hello.txt  查找/home目录下的hello.txt文件

	find /opt -user hercynians   查找/opt目录下，用户为hercynians的文件

	find / -size +200M  查找根目录下（整个系统）大于200M的文件

	 

###	10.2  locate

	locate可以快速定位文件路径，利用实现建立的系统中所有文件名称以及路径的locate数据库实现快速定位。为了保证查询结果的准确度，管理员需定期更新locate时刻

	基本语法：

	yum -y install mlocate (安装mlocate)

	updatedb  (创建、更新locate数据库)

	locate 文件

	 

###	10.3  which

	查看某个指令在哪个目录下

	基本语法：

	which 指令 （如which ls）

	 

###	10.4  grep

               grep 允许对文件进行横式查找，横式即正则表达式

	基本语法:

	grep [选项] 查找内容 源文件

                   

                   如: cat /home/hello.txt      | grep -n “yes” 

	或 grep-n “yes” /home/hello.txt  查找hello.txt内的yes并显示行号（高版本不需要引号）

	·     常用的两种模式查找

                   

	 

	 

##	11.0  压缩和解压

###	11.1  gzip和gunzip

	gzip用于压缩文件,gunzip用于解压文件

	基本语法：

	gzip 文件  （压缩文件，且格式为.gz）

	gunzip 文件 （解压文件）

###	11.2  zip和unzip（apt install zip下载zip命令）

	zip用于压缩，unzip用于解压

	基本语法:

	zip [选项] xxx.zip 将压缩的内容（将文件或目录压缩为...)

	-r 递归压缩，可压缩整个目录

	unzip [选项] xxx.zip (解压文件)

	-d <目录> 将文件解压至指定目录

	 

###	11.3  tar

	tar为打包指令，打包后的文件为xxx.tar.gz格式

	基本语法:

	tar [选项] xxx.tar.gz 需要打包的文件

	

	如:1、将/home/pig.txt和/home/cat.txt 压缩为pc.tar.gz

	tar -zcvf pc.tar.gz /home/pig.txt /home/cat.txt

	2、将/home/myhome.tar.gz 解压搭配/opt/tmp2目录下

tar -zxvf /home/myhome.tar.gz  -C  /opt/tmp2 (-C为解压到指定目录)

 

 

# 二、Linux组的概念和相应指令

##     1.0  组的概念

     Linux操作系统中，每个用户都必须存在一个组之中，每个文件都有对应的所有者、所在组和其他组的概念。文件所在组的用户都对该文件有相应的权限，其他组的用户也对该文件有相应的权限。

      文件刚创建时与创建者属于同一组

###     1.1  所有者

      修改文件所有者

      chown 新所有者 文件名   （改变所有者）

      chown 新所有者 新组 文件 （改变所有者和所在组）

      -R 可以递归更改

      如 chown -R tom group1 abb

      

##      1.2  所在组

##      组的创建

##      1创建组

      groupadd 组名

      2创建一个新用户并将其放入某组内

      useradd -g 组名 用户名

      3修改文件所在组

      chgrp 组名  文件名

      chgrp -R group2 /home/test

      所在组

      修改所在组

      usermod -g 新组名  用户名

      改变用户登录初始目录

      usermod -d 目录名  用户名 （注意：用户需要有进入该目录的权限）

 

##     2.0  权限

###     2.1  文件权限查看与介绍

     ls -l显示的内容如下

      -rwxrw-r-- 1 root group1 1213 Feb 2 09:39 abc

      第一列(0-9位字符)

      1、第0位确定文件类型(d、l、-、c、b)

      l为链接，类似快捷方式 （link）

      d为目录 (directory)

      c是字符设备文件，如鼠标键盘等 (character device)

      b是块设备，比如硬盘 (block device)

      - 是普通文件

      2、1-3位确定文件所有者拥有该文件的权限——user

      3、4-6位代表所属组（同用户组）拥有该文件的权限——group

      4、7-9位代表其他组对该文件拥有的权限——other

      

	rwx作用于文件

      [r]代表可读(read)：可以读取，查看

      [w]代表可写(write)：可以编辑，但不一定可删除，删除前提是对该目录有w权限

      [x]代表可执行(execute)：可以被执行

      rwx作用于目录

      [r]代表可读(read)：可以读取并使用ls指令查看

      [w]代表可写(write)：可以对该目录和目录内进行 创建、重命名、删除文件 

      [x]代表可执行(execute)：可以进入该目录

      其他说明

      1          文件：硬链接数  目录：子目录数

      root      用户（所有者）

      group1    文件所在组

      1213      文件大小

      Feb 2 09:39 最后修改日期

      abc       文件或目录名

 ##     2.2  权限修改

     chmod

      第一种方式: + - =修改权限

     u:所有者 g:所在组 o:其他人 a:所有人

      chmod u=rwx,g=rx,o=x 文件或目录   （指定权限）

      chmod o+w 文件或目录   （增加权限）

      chmod a-x 文件或目录    （删除权限）

      加和减可以在同一条指令内完成

      第二种方式：通过数字修改

      r=4 w=2 x=1 rwx则为7

      chmod u=rwx,g=rx,0=x 文件或目录  就相当于

      chmod 751 文件或目录

 

 

#  三、crond和at任务调度的使用

##     1.0  crond任务调度

     任务调度是系统在某时间执行的特定命令或程序

      分类：1、系统工作，有必要周而复始的执行的工作，如病毒扫描

         2、个别用户工作，个别用户希望执行某些程序，如对Mysql数据库的备份

      基本语法：

      crontab [选项]

      service crond restart 重启任务调度

      常用选项

 

      前5个占位符（五个”*”）：

 

      crond时间规则：

 

      案例：

 

 

##       2.0  at任务调度

     基本介绍：

	at命令是一次性定时计划任务，其守护进程atd会在后台执行，检查任务队列来进行。

      通常，atd每60秒检查一次任务队列，有作业时，会检查作业运行时间，如果运行时间与当前时间匹配，则运行此次作业。

      在执行at命令时，要保证atd进程处于启动状态，可以使用相关指令来查看

（如: ps -ef | grep atd）

      基本语法：

      at [选项] [时间]

      ctrl + d 结束at命令的输入

      atq 查看系统中有没有执行的工作任务

   atrm 任务编号 （删除已经设定的任务）

 

      at时间规则:



如在两天后的下午5点执行/bin/ls /home指令

at 5pm + 2 days

at> /bin/ls /home

两次ctrl + d 退出

      

# 四、磁盘

##     1.0  磁盘分区机制





查看当前磁盘分区情况：

lsblk 或 lsblk -f

	1.1  添加磁盘分区

	添加磁盘分区步骤：

	1、添加新硬盘并重启系统

	2、fdisk /dev/sdb(新磁盘名)

	3、开始对sdb分区

   m 显示命令列表

   p  显示磁盘分区

    n  新增分区

   d  删除分区

   w 写入并退出

	4、开始分区后输入n，新增分区，然后选择p，分区类型为主分区。两次回车默认剩余全部空间。最后输入w写入并退出。若不保存则输入q。按m可以显示命令列表

	格式化分区

	mkfs -t ext4 /dev/sdb1 (ext4为分区类型，sdb1为分区)

	挂载和卸载指令

	mount 设备名称  挂载点  （如 mount /dev/sdb1 /home/newdisk）

	unmount 设备名称 挂载点（设备名称可以省略，如unmount /home/newdisk） 

	注意：用命令行设置的挂载关系，会在系统重启后失效

	永久挂载

	vim /etc/fstab后，在对应位置修改信息

	添加完成后，执行mount -a即刻生效，或者重启后生效

	 

##	1.2  磁盘情况查询

	查询整体系统

	df -h 

	查询指定磁盘

	du -h <目录>

	-s 指定目录占用大小汇总

	-h 显示计量单位

	-a 显示文件

	-c 列出明细的同时，增加汇总值

	--max-depth=1 子目录深度

	实用指令

	1、统计/opt文件夹下的一般文件个数

	ls -l /opt | grep “^-” | wc -l

	2、统计/opt文件夹下的目录个数

	ls -l /opt | grep “^d” | wc -l

	3、统计/opt文件夹下的文件个数，包含子文件下的

	ls -lR /opt | grep “^d” | wc -l

	 

# 五、NAT网络配置

##	1.0  NAT原理简介

	NAT（Network Address Translation）为网络转换，主要用于转换公网和私网的ip地址



##      1.1  查看网络配置

      Linux系统下使用ifconfig (windows为ipconfig)

      ping + 网址 （可以测试与该网址之间的连接状况）

      1.2  配置网络环境

     编辑 vi /etc/sysconfig/network-scripts/ifcfg-ens33(此处为设备名，不唯一)

      将ip地址配置为静态

      1、找到BOOTPROTO=”dhcp” 将dhcp改为static (将自动分配改为静态分配)

      2、加入以下内容（网段自行编辑）：

      IPADDR=192.168.200.130 (ip地址)

      GATEWAY=192.168.200.2 (网关)

      DNS1=192.168.200.2 (域名解析器)

      3、在虚拟机的“编辑”一栏中，同样将ip地址进行对应

      重启网络服务指令：

      service network restart

     1.3  主机名和host映射

     修改主机名:

      指令hostname 查看主机名

      vim /etc/hostname 可修改主机名，修改后需要重启系统

      添加host映射

      hosts是一个文本文件，用来记录ip和主机名之间的映射关系

      /etc/hosts 中加入192.168.200.1 ThinkMac-PC (即ip地址和主机名)

      修改完成后即可通过主机名而非Ip进行连接

      DNS(Domain Name System)

      DNS为域名系统，是互联网上作为域名和ip地址相互映射的分布式数据库

 

 

# 六、进程

##     1.0  进程基本介绍

     Linux系统中，每个执行的程序都叫做一个进程，每个进程都分配一个ID号(pid,进程号)

      进程分为前台和后台，前台可以直接进行交互，而后台一般会常驻系统中直到关机。

##      1.1  显示系统执行的进程

     ps 指令用于查看系统中运行的进程和其状态

      常用选项

	

      各参数基本解释

 

      

##	1.2  终止进程

  <font color="red">    基本语法</font>

      kill [选项] 进程号

      killall 进程名称

      常用选项：

      -9 表示立刻强制进程停止运行

      如：

      1、踢掉某个非法登录用户

      用ps -aux | grep sshd查询用户进程号，然后kill 进程号。（sshd为远程登录服务）

      2、终止sshd服务，随后在适当时间重启

      用ps -aux | grep sshd查询找到/usr/sbin/sshd 的进程，然后kill 进程号

      以/bin/systemctl start sshd.service 启动sshd服务

      3、强制关闭一个终端

      ps -aux | grep bash 来根据时间判断终端打开的顺序

      kill -9 进程号，来关闭终端

  ##    1.3  查看进程树

     pstree 指令来查看进程树

      常用选项

      -p 显示进程的pid

      -u 显示进程的所属用户

 

##      2.0  服务管理

     服务(service)本质就是进程，但是运行在后台，通常会监听某个端口，等待其他程序的请求（如Mysql客户端连接时通过3306端口对mysqld服务发起请求，xshell客户端通过22端口对sshd服务发起请求）也称之为守护进程。

##     2.1  service命令

 <font color="red">	基本语法</font>

      service 服务名  [ start | stop | restart | reload | status ]

      注意：在CentOS 7.0以后的系统中，很多服务不是用service而是用systemctl

      可以通过service管理的服务通过/etc/init.d查看

      查看服务

      1、setup，会进入编辑模式，带有[*]的服务是开机自启动服务,光标放到*上输入空格则可取消自启动

      （找不到命令则yum install setuptool）

      2、进入/etc/init.d 查看可用service控制的服务

##      2.2  chkconfig命令

 <font color="red">开机流程：</font>



      给服务的各个级别设置自启动/关闭

      chkconfig --list 可查看chkconfig命令管理的服务

      chkconfig --level 5 服务名 on/off (在运行级别5时管理某一服务的开或关)

      注意：需要在重启后生效

      （在CentOS 7.0以后的版本中，很多服务通过systemctl管理）

##      2.3  systemctl 命令

  <font color="red">基本语法</font>

      systemctl [ start | stop | restart | status ] 服务名

      systemctl命令管理的服务可在/usr/lib/system/system 中查看

      设置服务的自启动状态

      systemctl list-unit-files 可以查看服务的自启动状态

      systemctl enable 服务名 (设置服务开机启动)

      systemctl disable 服务名 (关闭服务开机启动)

      systemctl is-enabled 服务名 (查询某个服务是否自启动)

      2.4  firewall 命令

      打开或关闭指定窗口

      firewall-cmd --permanent --add-port=端口号/协议 （打开端口）

      firewall-cmd --permanent --remove-port=端口号/协议 （关闭端口）

      firewall-cmd --reload (重新载入，需要重新载入才能使防火墙的相关修改生效)

      firewall-cmd --query-port=端口/协议 （查询端口是否开放）

 

##      3.0  动态监控进程

     通过top命令来动态监控进程，top命令与ps命令很相似，都用来显示正在执行的进程。top与ps不同之处在于top在执行一段时间后可以更新正在运行的程序。

##      3.1  top命令

     基本语法

      top [选项]

	

	操作交互（注意大小写）

	

	输入u,再输入用户名，可以查看相应用户的进程

	输入k，在输入进程号，可以关闭相应进程

	 

	https://www.cnblogs.com/wj78080458/p/10584540.html top显示进程信息

	https://blog.csdn.net/yjclsx/article/details/81508455 top命令参数详解

	参数基本解释

	

第1行：top - 05:43:27 up 4:52, 2 users, load average: 0.58, 0.41, 0.30 

 第1行是任务队列信息，其参数如下：



load average: 如果这个数除以逻辑CPU的数量，结果高于5的时候就表明系统在超负荷运转了。 

第2行：Tasks: 159 total, 1 running, 158 sleeping, 0 stopped, 0 zombie 

第3行：%Cpu(s): 37.0 us, 3.7 sy, 0.0 ni, 59.3 id, 0.0 wa, 0.0 hi, 0.0 si, 0.0 st 

第2、3行为进程和CPU的信息 

当有多个CPU时，这些内容可能会超过两行，其参数如下：





第4行：KiB Mem: 1530752 total, 1481968 used, 48784 free, 70988 buffers 

第5行：KiB Swap: 3905532 total, 267544 used, 3637988 free. 617312 cached Mem 

第4、5行为内存信息 

其参数如下：



进程信息：







 

## 4.0  监控网络状态

使用netstat来监控网络状态。ping 地址 来检测连接状况

基本语法：

netstat [选项]

常用选项：

-an 按一定顺序排列输出

-p 显示哪个进程正在调用

 

# 七、文件安装和卸载

 ##    1.1  rpm命令

     rpm（RedHat Package Manager）用于互联网下载包的打包以及安装，它在某些Linux发行版中生成具有.RPM扩展名的文件.

      常用命令

      rpm -qa | grep xx 查询已安装的rpm列表

      rpm -q 软件包名 （查询软件包是否安装）

      rpm -qi 软件包名 （查询软件包信息）

      rpm -ql 软件包名 （查询软件包中包含的文件）

    rpm -qf 文件全路径名 （查询文件所属的软件包）

      rpm -e 软件包名 （erase卸载软件包,增加参数—nodeps可以强制删除）

      rpm -ivh 软件包全路径名 (安装rpm包,install安装 verbose提示 hash进度条)

      rpm包名基本格式

 

 

 

##      1.2  yum命令

     yum是shell前端软件包管理器，基于rpm包管理，能够从指定的服务器自动下载rpm包并安装，可以自动处理依赖关系，并且一次性安装所有依赖的软件包。

      常用命令

      yum list 查询yum（服务器是否有需要安装的软件）

      yum install 软件名 （下载安装）

      

      JDK安装

 

 

# 八、日志管理

##     4.0  系统常用日志

     /var/log是绝大多数系统日志文件保存目录

![在这里插入图片描述](https://img-blog.csdnimg.cn/95e4b64bd9604845a95e2170d1b9f45f.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/73aacc66c06042ad9a2fc3ec99555c1d.png)


赶紧学起来，一天不学习浑身难受。，，，
点赞收藏，备用学习哦
