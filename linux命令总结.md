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

