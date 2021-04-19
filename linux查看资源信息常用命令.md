### 系统

 uname -a               # 查看内核/操作系统/CPU信息
 
 lsb_release -a         # 查看操作系统版本 (适用于所有的linux，包括Redhat、SuSE、Debian等发行版，但是在debian下要安装lsb)   

cat /proc/cpuinfo      # 查看CPU信息

hostname               # 查看计算机名

lspci -tv              # 列出所有PCI设备

lsusb -tv              # 列出所有USB设备

lsmod                  # 列出加载的内核模块

env                    # 查看环境变量

## 资源


free -m                # 查看内存使用量和交换区使用量

df -h                  # 查看各分区使用情况

du -sh <目录名>        # 查看指定目录的大小

grep MemTotal /proc/meminfo   # 查看内存总量

grep MemFree /proc/meminfo    # 查看空闲内存量

uptime                 # 查看系统运行时间、用户数、负载

cat /proc/loadavg      # 查看系统负载

## 磁盘和分区


mount | column -t      # 查看挂接的分区状态

fdisk -l               # 查看所有分区

swapon -s              # 查看所有交换分区

hdparm -i /dev/hda     # 查看磁盘参数(仅适用于IDE设备)

dmesg | grep IDE       # 查看启动时IDE设备检测状况

## 网络

ifconfig               # 查看所有网络接口的属性

iptables -L            # 查看防火墙设置

route -n               # 查看路由表

netstat -lntp          # 查看所有监听端口

netstat -antp          # 查看所有已经建立的连接

netstat -s             # 查看网络统计信息

netstat -nat | grep -i "7090"   # 查看网络端口连接明细  

netstat -nat | grep -i "7090" | grep "TIME_WAIT" | wc -l  # 查看网络端口 7090 状态 TIME_WAIT 的统计个数 

netstat -an | grep 7090 | awk '/^tcp/ {++S[$NF]} END {for(a in S) print a, S[a]}'   # 查看端口 连接状态统计个数

LISTEN：      侦听来自远方的TCP端口的连接请求

SYN-SENT：    再发送连接请求后等待匹配的连接请求

SYN-RECEIVED：再收到和发送一个连接请求后等待对方对连接请求的确认

ESTABLISHED： 代表一个打开的连接

FIN-WAIT-1：  等待远程TCP连接中断请求，或先前的连接中断请求的确认

FIN-WAIT-2：  从远程TCP等待连接中断请求

CLOSE-WAIT：  等待从本地用户发来的连接中断请求

CLOSING：     等待远程TCP对连接中断的确认

LAST-ACK：    等待原来的发向远程TCP的连接中断请求的确认

TIME-WAIT：   等待足够的时间以确保远程TCP接收到连接中断请求的确认

CLOSED：      没有任何连接状态

## 进程

ps -ef                 # 查看所有进程

top                    # 实时显示进程状态

ps aux | less

 -A：显示所有进程

  a：显示终端中包括其它用户的所有进程

 x：显示无控制终端的进程

## 用户

w                      # 查看活动用户

id <用户名>            # 查看指定用户信息

last                   # 查看用户登录日志

cut -d: -f1 /etc/passwd   # 查看系统所有用户

cut -d: -f1 /etc/group    # 查看系统所有组

crontab -l             # 查看当前用户的计划任务

## 服务

chkconfig --list       # 列出所有系统服务

chkconfig --list | grep on    # 列出所有启动的系统服务

## 程序

rpm -qa                # 查看所有安装的软件包

## 文件编辑

sed -i 就是直接对文本文件进行操作的。

sed -i 's/原字符串/新字符串/' /home/1.txt
sed -i 's/原字符串/新字符串/g' /home/1.txt

## 文件统计 

cat access.log  | awk '{print $2,$3}' | sort | uniq -c    
