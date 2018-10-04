# Elastic Search 

### Cluster Nodes

```
curl  http://localhost:9200/_cat/nodes?v
ip           heap.percent ram.percent cpu load_1m load_5m load_15m node.role master name
172.31.3.119           54          99  13    3.51    2.07     1.95 mdi       -      elasticsearch-0
172.31.1.84            73          74  19    2.39    1.85     1.76 mdi       *      elasticsearch-1
172.31.2.102           14          89  21    3.03    3.30     3.57 mdi       -      elasticsearch-4
172.31.2.101           28          89  26    3.03    3.30     3.57 mdi       -      elasticsearch-2
172.31.3.120           13          99  14    3.51    2.07     1.95 mdi       -      elasticsearch-3
```

### Check Health

```
[root@elasticsearch-0 elasticsearch]# curl  http://localhost:9200/_cat/health?v
epoch      timestamp cluster               status node.total node.data shards pri relo init unassign pending_tasks max_task_wait_time active_shards_percent
1532414602 06:43:22  elasticsearch-cluster green           5         5    320 160    0    0        0             0                  -                100.0%

```

### List Pipelines

```
curl -X GET "localhost:9200/_ingest/pipeline"
```

### Snapshotting

* Turn on snapshot repository (S3)

```
curl -X PUT "localhost:9200/_snapshot/xxxxx-snapshot" -H 'Content-Type: application/json' -d'
{
  "type": "s3",
  "settings": {
    "bucket": "bucket name",
    "region": "us-west",
    "access_key": "xxxxxxxxxxxxxxxxxx",
    "secret_key": "xxxxxxxxxxxxxxxxxxxx"
  }
}
'
```

* Do snapshot of specified indices

```
curl -X PUT "localhost:9200/_snapshot/xxxxx-snapshot/snapshot-name?wait_for_completion=true" -H 'Content-Type: application/json' -d'
 {
   "indices": "test_index-2018.07.24",
   "ignore_unavailable": true,
   "include_global_state": false
 }
 '
```
