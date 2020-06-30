## Clean stale kubelet mounts

``` tab="Command"
for  m in $( mount| grep secret | awk '{print $3}' ); do 
    sudo umount $m
done
```

```bash tab="Output"

```
