## Explain unassigned shards

``` tab="curl"
curl -XGET 0:9200/_cluster/allocation/explain
```

```bash tab="console"
GET _cluster/allocation/explain
```

## Disk usage on nodes

``` tab="curl"
curl -XGET 0:9200/_cat/allocation?v&s=disk.percent:desc
```

```bash tab="console"
GET _cat/allocation?v&s=disk.percent:desc
```
