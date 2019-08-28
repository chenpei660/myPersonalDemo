## 常用Linux命令总结
# 查找类 
1、 在文件中查找关键字，并且展示上下10行  cat <filename> |grep '关键字'  -C 10 
2、 当前目录文件查找关键字   grep -r '关键字' ./ 


# 接口调试类
1、 发送远程接口 curl 
    <br>FORM 提交
    <br>-X 这个参数可以配置HTTP的方法
    <br>curl -X POST 127.0.0.1:7001/api/material/update
    <br>curl -X POST --data "name=kk&name2=gg" 127.0.0.1:7001/api/material/create # 带参数的post提交
 <br> 2、 其他处理head、cookie 等见 https://www.cnblogs.com/sea24/articles/10108879.html 
 
 #  测试ip的防火墙
 telnet [源ip]  [目的ip] [目的端口]
 
 # 按照工具包 
 yum install telnet -y 
