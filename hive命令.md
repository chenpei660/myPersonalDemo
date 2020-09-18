# hive 目录操作
<br> 查询目录：hdfs dfs -ls /user/hive/warehouse/anan.db/customizefunction
<br> 删除目录：hdfs dfs -rm /user/hive/warehouse/anan.db/customizefunction
<br> 创建目录：hdfs dfs -mkdir /user/hive/warehouse/anan.db/customizefunction

# 创建hive 永久函数 
<br> 进入hive 命令行，使用对应数据库 use anan;
<br> 上传jar 包到hive 目录：
<br>hdfs dfs -put /home/anan_uat/jar/hive.customize.function-1.0-SNAPSHOT.jar /user/hive/warehouse/anan.db/customizefunction

<br> 创建永久函数：
<br>create function doCalcPolicyYear as 'com.graphene.report.bcp.CalcPolicyYear' using jar '/user/hive/warehouse/anan.db/customizefunction/hive.customize.function-1.0-SNAPSHOT.jar'

<br> 查看函数 show functions;

