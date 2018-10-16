# Hadoop 

### HDFS health report

```
hdfs dfsadmin -report
```

### Basic operrations 

```
hdfs dfs -ls /dataset/
hdfs dfs -put TrafficSpeeds.csv /dataset/
hdfs dfs -put Crimes.csv /dataset/
```

### Import files with provided replication factor

```
 hdfs dfs -D dfs.replication=8 -put * /datasets/
```

