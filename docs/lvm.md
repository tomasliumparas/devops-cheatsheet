## Create thin pool
```
lvcreate --poolmetadatasize 1G --thin myvg/mythinpool --size 100m
```

## Create Thin LV
```
lvcreate --thin myvg/mythinpool --virtualsize 1g --name mythinvol
```

## Resize thin metada:
```
lvextend --poolmetadatasize +1G /dev/data_vg/tp_media
```

!!! tip
    Do not forget to verify `pmspare` size
    If `pmspare < tp_metadata` remove it and recreate:
    ```
    lvremove lvremove data_vg/lvol0_pmspare
    lvconvert --repair data_vg/tp_media
    ```
