[toc]

# Sources 配置项
- [Sources 配置项](#sources-配置项)
    - [spoldir  sources](#spoldir--sources)
    - [Avro sources](#avro-sources)
    - [Exec sources](#exec-sources)
    - [netcat sources](#netcat-sources)
- [Channels 配置项](#channels-配置项)
    - [file channels](#file-channels)
    - [memory channels](#memory-channels)
- [sinks 配置项](#sinks-配置项)
    - [hdfs sinks](#hdfs-sinks)
    - [logger sinks](#logger-sinks)
    - [avro sinks](#avro-sinks)

### spoldir  sources

```shell
jyp15.sources.r1.type=spooldir
jyp15.sources.r1.spoolDir=/root/jyp/data
jyp15.sources.r1.fileSuffix=.over
jyp15.sources.r1.deletePolicy=never
jyp15.sources.r1.fileHeader=true
jyp15.sources.r1.fileHeaderKey=path
jyp15.sources.r1.basenameHeader=true
jyp15.sources.r1.basenameHeaderKey=filename
jyp15.sources.r1.includePattern=\\S.*(txt|json)
jyp15.sources.r1.ignorePattern=\\S.*(over|tmp)
jyp15.sources.r1.batchSize= 100
jyp15.sources.r1.pollDelay=1000
jyp15.sources.r1.recursiveDirectorySearch=true

```

### Avro sources

````shell

jyp15.sources.r1.type=avro
jyp15.sources.r1.bind=0.0.0.0								#IP地址
jyp15.sources.r1.port=1026									#端口
````

### Exec sources

````shell
jyp15.sources.r1.type= exec
jyp15.sources.r1.command= tail -F /var/log/syslog						 #要执行的外部命令,该命令的输出将作为事件发送
jyp15.sources.r1.restart= true															#命令执行退出后是否重新启动命令,默认false不重启
jyp15.sources.r1.batchSize= 20														#每批发送的事件数目
````

### netcat sources

````shell
jyp15.sources.r1.type=netcat
jyp15.sources.r1.bind=localhost							 #IP地址/映射绑定的主机名
jyp15.sources.r1.port=44444							      #绑定的端口	
jyp15.sources.r1.ack-every-event= true				#是否每接收一个事件就发送确认数据
````



# Channels 配置项

### file channels

```shell
jyp15.channels.c3.type=file
jyp15.channels.c3.dataDirs=/home/jyp/filechannelTwo/data
jyp15.channels.c3.checkpointDir=/home/jyp/filechannelTwo/checkpoint
jyp15.channels.c3.transactionCapacity=10000
jyp15.channels.c3.capacity=100000
jyp15.channels.c3.checkpointInterval=30000
```

### memory channels

```shell
jyp15.channels.c4.type=memory
jyp15.channels.c4.capacity=10000
jyp15.channels.c4.transactionCapacity = 100
```



# sinks 配置项

### hdfs sinks

````shell
jyp15.sinks.s4.type=hdfs
jyp15.sinks.s4.hdfs.path=hdfs://192.168.84.15:8020/bigdata/%y-%m-%d/%H-%M
jyp15.sinks.s4.hdfs.filePrefix= log-
jyp15.sinks.s4.hdfs.fileSuffix= .bigdata
jyp15.sinks.s4.hdfs.inUsePrefix= flum-
jyp15.sinks.s4.hdfs.inUseSuffix= .tmp
jyp15.sinks.s4.hdfs.rollCount=10
jyp15.sinks.s4.hdfs.rollSize=0
jyp15.sinks.s4.hdfs.rollInterval= 0
jyp15.sinks.s4.hdfs.batchSize= 100
jyp15.sinks.s4.hdfs.useLocalTimeStamp=true
jyp15.sinks.s4.hdfs.writeFormat= Text
jyp15.sinks.s4.hdfs.fileType= DataStream
jyp15.sinks.s4.hdfs.threadsPoolSize= 10
jyp15.sinks.s4.hdfs.idleTimeout= 10
jyp15.sinks.s4.hdfs.round= true
jyp15.sinks.s4.hdfs.roundValue= 10
jyp15.sinks.s4.hdfs.roundUnit= miunte
````

### logger sinks

````shell
jyp15.sinks.s5.type= logger
jyp15.sinks.s5.maxBytesToLoge=123
````

### avro sinks

````shell
jyp15.sinks.s6.type=avro
jyp15.sinks.s6.hostname=localhost
jyp15.sinks.s6.port=1025									#连接对应sources的端口
````




