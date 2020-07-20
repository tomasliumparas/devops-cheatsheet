## Settings
``` tab="curl"
curl -XGET 0:9200/_cluster/settings
```

```bash tab="console"
GET _cluster/settings
```

## Health
``` tab="curl"
curl -XGET 0:9200/_cluster/health
```

```bash tab="console"
GET _cluster/health
```

## Allocation

``` tab="curl"
curl -XGET 0:9200/_cat/allocation?v
```

```bash tab="console"
GET _cat/allocation?v
```

### Nodes by disk usage

``` tab="curl"
curl -XGET 0:9200/_cat/allocation?v&s=disk.percent:desc
```

```bash tab="console"
GET /_cat/allocation?v&s=disk.percent:desc
```

### Explain unassigned shards

``` tab="curl"
curl -XGET 0:9200/_cluster/allocation/explain
```

```bash tab="console"
GET _cluster/allocation/explain
```

## Nodes

``` tab="curl"
curl -XGET 0:9200/_cat/nodes?v
```

```bash tab="console"
GET _cat/nodes?v
```

### Aattributes

``` tab="curl"
curl -XGET 0:9200/_cat/nodeattrs
```

```bash tab="console"
GET _cat/nodeattrs
```

### Uptime

``` tab="curl"
curl -XGET 0:9200/_cat/nodes?v&h=ip,role,name,uptime,file_desc.percent&s=uptime
```

```bash tab="console"
GET _cat/nodes?v&h=ip,role,name,uptime,file_desc.percent&s=uptime
```

### Indexing perations

``` tab="curl"
curl -XGET 0:9200/_cat/nodes?v&h=ip,role,name,uptime,indexing.index_total,indexing.index_failed&s=uptime
```

```bash tab="console"
GET _cat/nodes?v&h=ip,role,name,uptime,indexing.index_total,indexing.index_failed&s=uptime
```

## Indices

``` tab="curl"
curl -XGET 0:9200/_cat/indices?v
```

```bash tab="console"
GET _cat/indices?v
```

### By size

``` tab="curl"
curl -XGET 0:9200/_cat/indices?v&h=health,status,index,pri,rep,docs.count,store.size&s=store.size:desc
```

```bash tab="console"
GET _cat/indices?v&h=health,status,index,pri,rep,docs.count,store.size&s=store.size:desc
```

## Shards

``` tab="curl"
curl -XGET 0:9200/_cat/shards?v
```

```bash tab="console"
GET _cat/shards?v
```

### By size

``` tab="curl"
curl -XGET 0:9200/_cat/shards?v&s=store:desc
```

```bash tab="console"
GET _cat/shards?v&s=store:desc
```

### By state

``` tab="curl"
curl -XGET 0:9200/_cat/shards?h=index,shard,prirep,state,node,unassigned.reason&v&s=state
```

```bash tab="console"
GET _cat/shards?h=index,shard,prirep,state,node,unassigned.reason&v&s=state
```
