## Start all volumes
```
for volume in $(gluster v list); \
  do gluster v start $volume force; \
done
```
