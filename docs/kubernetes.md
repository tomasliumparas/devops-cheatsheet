## kubernetes.io Labels, Annotations and Taints

* `topology.kubernetes.io/zone`
* `topology.kubernetes.io/region`
* `node-role.kubernetes.io/<role>`


## Clean stale kubelet mounts

``` tab="Command"
for  m in $( mount| grep secret | awk '{print $3}' ); do 
    sudo umount $m
done
```

```bash tab="Output"

```
