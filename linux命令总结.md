## 常用Linux命令总结
# 查找类 
<br>1、 在文件中查找关键字，并且展示上下10行  cat <filename> |grep '关键字'  -C 10 
<br>2、 当前目录文件查找关键字   grep -r '关键字' ./ 


# 接口调试类
1、 发送远程接口 curl 
    <br>FORM 提交
    <br>-X 这个参数可以配置HTTP的方法
    <br>curl -X POST 127.0.0.1:7001/api/material/update
    <br>curl -X POST --data "name=kk&name2=gg" 127.0.0.1:7001/api/material/create # 带参数的post提交
 <br> 2、 其他处理head、cookie 等见 https://www.cnblogs.com/sea24/articles/10108879.html 
 
命令行执行http请求： 
curl -H "Content-Type:application/json" -X POST -d '{"customerId":4,"orderNo":"61201909240029989202","queryOnlyOrder":false}' http://policy-anan-order-uat.pre.anan.net/order/queryOrderInfo
 
 #  测试ip的防火墙
 telnet [源ip]  [目的ip] [目的端口]
 
 # 按照工具包 
 yum install telnet -y 
 
 # xshell 常用命令方法
<br>1、 输入sz 文件路径即下载该文件到本地收藏夹的下载目录。下载目录可配置 
<br>2、 上传，在xshell上输入:rz -be，就会弹出本地文件选择框界面
<br>3、执行sh 文件  
<br>   当前路径 ./脚本名    
<br>   sh 完整路径及脚本名   
<br>   sh 脚本名

# linux sudo chmod 
chmod abc file
<br>其中a,b,c各为一个数字，分别表示User、Group、及Other的权限。
<br>r=4，w=2，x=1
<br>https://www.cnblogs.com/shangzhijian/p/4730408.html

#  修改文件目录 owner  group
chown -R file1 file2 
<br>  -R  递归 
<br> chgrp -R file1 file2
<br> 
<br>chown -hR username:groupname ./目录名
<br>其中：h表示对符号链接也起作用；
<br>R表示对所有子文件也起作用；
<br>后面的用户名和组名用冒号分割；
<br>最后是要修改的目标文件夹；
<br>如有疑惑，在终端 man chown

#   Linux 按时间批量删除文件（删除N天前文件）  
<br> find /home/lifeccp/dicom/studies -mtime +21 -name "*.*" -exec rm -Rf {} \;
<br>  https://www.cnblogs.com/hurry-up/p/9777261.html  

#   清空文件夹
<br>   rm -rf *

# 解压 文件 
<br>  tar -xzvf file.tar.gz 
<br>  tar –xvf file.tar  解压 tar包
<br>  tar -xzvf azkaban-exec-server-0.1.0-SNAPSHOT.tar.gz
<br>  tar -xzvf azkaban-web-server-0.1.0-SNAPSHOT.tar.gz  
<br>  tar -zcvf renwolesshel.tar.gz /renwolesshel    打包成tar.gz格式压缩包

# 批量替换文件内容
<br>   替换每行第一次出现的字符串
<br>   sed -i 's/查找的字符串/替换的字符串/' 文件
 
<br>    替换文件中所有出现过的字符串
<br>    sed -i 's/查找的字符串/替换的字符串/g' 文件


# Linux修改密码用
<br> passwd 命令，用root用户运行passwd ，passwd user_name可以设置或修改任何用户的密码，普通用户运行passwd只能修改它自己的密码。


# 查找文件 
查找目录：find /（查找范围） -name '查找关键字' -type d
查找文件：find /（查找范围） -name 查找关键字 -print


