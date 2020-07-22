## Resource pool usage

``` sql tab="Command"
SELECT pool_id
   , Name
   , min_memory_percent
   , max_memory_percent
   , max_memory_kb/1024 AS max_memory_mb
   , used_memory_kb/1024 AS used_memory_mb  
   , target_memory_kb/1024 AS target_memory_mb
FROM sys.dm_resource_governor_resource_pools
go
```

```bash tab="Output"
TBD
```

## Index bucket count usage

``` sql tab="Command"
SELECT  
   obj.name as '_object_name'
   , i.name as 'index_name'
   ,total_bucket_count - empty_bucket_count as use_bucket_count
   ,total_bucket_count
   ,floor((cast(empty_bucket_count as float)/total_bucket_count) * 100) as 'empty_bucket_percent'
FROM sys.dm_db_xtp_hash_index_stats as hs
JOIN sys.indexes as i
ON hs.object_id=i.object_id and hs.index_id=i.index_id
JOIN sys.objects as obj on
obj.object_id = hs.object_id
```

```bash tab="Output"
TBD
```
