## Resource pool usage

=== "Command"
    ``` sql
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

=== "Output"
    ```bash
    TBD
    ```

## Index bucket count usage

=== "Command"
    ``` sql
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

=== "Output"
    ```bash
    TBD
    ```


## Index bucket and chains usage

=== "Command"
    ``` sql
    SELECT  
      QUOTENAME(SCHEMA_NAME(t.schema_id)) + N'.' + QUOTENAME(OBJECT_NAME(h.object_id)) as [table],   
      i.name                   as [index],   
      h.total_bucket_count,  
      h.empty_bucket_count,  

      FLOOR((  
        CAST(h.empty_bucket_count as float) /  
          h.total_bucket_count) * 100)  
                                as [empty_bucket_percent],  
      h.avg_chain_length,   
      h.max_chain_length  
    FROM  
            sys.dm_db_xtp_hash_index_stats  as h   
      JOIN sys.indexes                     as i  
              ON h.object_id = i.object_id  
              AND h.index_id  = i.index_id  
    JOIN sys.memory_optimized_tables_internal_attributes ia ON h.xtp_object_id=ia.xtp_object_id
    JOIN sys.tables t on h.object_id=t.object_id
    WHERE ia.type=1
    ORDER BY [table], [index];
    ```

=== "Output"
    ```bash
    TBD
    ```
