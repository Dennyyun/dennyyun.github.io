# HADOOP hdfs操作

> **创建目录**  :

````shell
Hadoop  fs  -mkdir  /test								#在hdfs 根目录创建test文件夹（目录）
````



> **查看`test.txt`  文件的内容**  ：

````shell
hadop fs  -cat  /test.txt
````



> **列出根目录下的所有列表**   ：

````shell
hadoop fs -ls   /
````



> **从本地上传到hdfs根目录**  ：

````shell
hadoop  fs  -put   test.txt    /						#从本地上传test.txt 文件到hdfs 根目录
````



> **从hdfs 下载到本地**  ：

```shell
hadoop  fs  -get  /test.txt    /						#从hdfs下载test.txt 文件到本地
```



> **从本地剪贴到hdfs根目录**  :

```sehll
hadoop   fs  -MoveFromLocal    test.txt   /   
```

