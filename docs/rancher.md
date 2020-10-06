## Retry node registration

=== "Command"
    ```
    systemctl stop docker
    systemctl stop containerd
    rm -rf /var/lib/docker/*
    rm -rf /var/lib/rancher/*
    rm -rf /etc/kubernetes
    df -h
    systemctl start docker
    ```

=== "Output"
    ```bash
    TBD
    ```
