## Cluster

### Settings
=== "curl"
    ```
    curl -XGET 0:9200/_cluster/settings
    ```

=== "console"
    ```bash
    GET _cluster/settings
    ```

### Health
=== "curl"
    ```
    curl -XGET 0:9200/_cluster/health
    ```

=== "console"
    ```bash
    GET _cluster/health
    ```

## Allocation

=== "curl"
    ```
    curl -XGET 0:9200/_cat/allocation?v
    ```

=== "console"
    ```bash
    GET _cat/allocation?v
    ```

### Nodes by disk usage

=== "curl"
    ```
    curl -XGET 0:9200/_cat/allocation?v&s=disk.percent:desc
    ```

=== "console"
    ```bash
    GET /_cat/allocation?v&s=disk.percent:desc
    ```

### Explain unassigned shards

=== "curl"
    ```
    curl -XGET 0:9200/_cluster/allocation/explain
    ```

=== "console"
    ```bash
    GET _cluster/allocation/explain
    ```

## Nodes

=== "curl"
    ```
    curl -XGET 0:9200/_cat/nodes?v
    ```

=== "console"
    ```bash
    GET _cat/nodes?v
    ```

### Aattributes

=== "curl"
    ```
    curl -XGET 0:9200/_cat/nodeattrs
    ```

=== "console"
    ```bash
    GET _cat/nodeattrs
    ```

### Uptime

=== "curl"
    ```
    curl -XGET 0:9200/_cat/nodes?v&h=ip,role,name,uptime,file_desc.percent&s=uptime
    ```

=== "console"
    ```bash
    GET _cat/nodes?v&h=ip,role,name,uptime,file_desc.percent&s=uptime
    ```

### Indexing perations

=== "curl"
    ```
    curl -XGET 0:9200/_cat/nodes?v&h=ip,role,name,uptime,indexing.index_total,indexing.index_failed&s=uptime
    ```

=== "console"
    ```bash
    GET _cat/nodes?v&h=ip,role,name,uptime,indexing.index_total,indexing.index_failed&s=uptime
    ```

## Indices

=== "curl"
    ```
    curl -XGET 0:9200/_cat/indices?v
    ```

=== "console"
    ```bash
    GET _cat/indices?v
    ```

### By size

=== "curl"
    ```
    curl -XGET 0:9200/_cat/indices?v&h=health,status,index,pri,rep,docs.count,store.size&s=store.size:desc
    ```

=== "console"
    ```bash
    GET _cat/indices?v&h=health,status,index,pri,rep,docs.count,store.size&s=store.size:desc
    ```

## Shards

=== "curl"
    ```
    curl -XGET 0:9200/_cat/shards?v
    ```

=== "console"
    ```bash
    GET _cat/shards?v
    ```

### By size

=== "curl"
    ```
    curl -XGET 0:9200/_cat/shards?v&s=store:desc
    ```

=== "console"
    ```bash
    GET _cat/shards?v&s=store:desc
    ```

### By state

=== "curl"
    ```
    curl -XGET 0:9200/_cat/shards?h=index,shard,prirep,state,node,unassigned.reason&v&s=state
    ```

=== "console"
    ```bash
    GET _cat/shards?h=index,shard,prirep,state,node,unassigned.reason&v&s=state
    ```


## Maintenance

### Clear cache

=== "curl"
    ```
    curl -XPOST localhost:9200/_cache/clear
    ```

=== "console"
    ```bash
    POST _cache/clear
    ```
    

