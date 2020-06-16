## Create thin pool
``` tab="Command"
lvcreate --poolmetadatasize 1G --thin myvg/mythinpool --size 100m
```

```bash tab="Output"
TBD
```
## Create Thin LV
``` tab="Command"
lvcreate --thin myvg/mythinpool --virtualsize 1g --name mythinvol
```

```bash tab="Output"
TBD
```
## Resize thin metada:
``` tab="Command"
lvextend --poolmetadatasize +1G /dev/data_vg/tp_media

```

```bash tab="Output"
TBD
```

!!! tip
    Do not forget to verify `pmspare` size
    If `pmspare < tp_metadata` remove it and recreate:
    ```
    lvremove lvremove data_vg/lvol0_pmspare
    lvconvert --repair data_vg/tp_media
    ```
