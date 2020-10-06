## Logical volumes

### Resize LV with all free space left in VG
=== "Command"
    ```bash
    lvresize --extents +100%FREE datavg/dockerlv --resizefs
    ```

=== "Output"
    ```bash
      Size of logical volume datavg/dockerlv changed from 28.00 GiB (7168 extents) to <33.00 GiB (8447 extents).
      Logical volume datavg/dockerlv successfully resized.
    meta-data=/dev/mapper/datavg-dockerlv isize=512    agcount=14, agsize=524288 blks
             =                       sectsz=512   attr=2, projid32bit=1
             =                       crc=1        finobt=0 spinodes=0
    data     =                       bsize=4096   blocks=7340032, imaxpct=25
             =                       sunit=0      swidth=0 blks
    naming   =version 2              bsize=4096   ascii-ci=0 ftype=1
    log      =internal               bsize=4096   blocks=2560, version=2
             =                       sectsz=512   sunit=0 blks, lazy-count=1
    realtime =none                   extsz=4096   blocks=0, rtextents=0
    data blocks changed from 7340032 to 8649728
    ```

## Thin pools

### Create thin pool

=== "Command"
    ```
    lvcreate --poolmetadatasize 1G --thin myvg/mythinpool --size 100m
    ```

=== "Output"
    ```bash
    TBD
    ```
### Create Thin LV

=== "Command"
    ``` tab="Command"
    lvcreate --thin myvg/mythinpool --virtualsize 1g --name mythinvol
    ```

=== "Output"
    ```bash tab="Output"
    TBD
    ```
### Resize thin metada:

=== "Command"
    ```
    lvextend --poolmetadatasize +1G /dev/data_vg/tp_media

    ```

=== "Output"
    ```bash
    TBD
    ```

!!! tip
    Do not forget to verify `pmspare` size
    If `pmspare < tp_metadata` remove it and recreate:
    ```
    lvremove lvremove data_vg/lvol0_pmspare
    lvconvert --repair data_vg/tp_media
    ```
