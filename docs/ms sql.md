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
