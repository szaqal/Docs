# Hive

```
hive --hiveconf hive.root.logger=INFO,console
```

```
hive> CREATE EXTERNAL TABLE IF NOT EXISTS Crimes(ID INT, Case_Number STRING, daate STRING, Block STRING, IUCR STRING, Primary_Type STRING, Description STRING, Location_Description STRING, Arrest STRING, Domestic STRING, Beat STRING, District STRING, Ward STRING, Community_Area STRING, FBI_Code STRING, X_Coordinate STRING, Y_Coordinate STRING, Year STRING, Updated_On STRING, Latitude STRING, Longitude STRING, Location STRING) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE LOCATION '/user/username/names';

hive> LOAD DATA INPATH '/datasets/Crimes.csv' INTO TABLE Crimes;
```

Relevant settings 

```
set mapreduce.input.fileinputformat.split.maxsize=14000000;
set hive.merge.mapfiles=true;
set hive.map.aggr.hash.percentmemory=0.5;
set hive.smbjoin.cache.rows=10000;
```
