## kubernetes.io Labels, Annotations and Taints

* `topology.kubernetes.io/zone`
* `topology.kubernetes.io/region`
* `node-role.kubernetes.io/<role>`


## Clean stale kubelet mounts

=== "Command"
    ```bash
    for  m in $( mount| grep secret | awk '{print $3}' ); do
        sudo umount $m
    done
    ```

=== "Output"
    ```bash

    ```
    
## Decode all secret keys

=== "Command"
    ```bash
    kubectl -o go-template='
    {{range $k,$v := .data}}{{printf "%s: " $k}}{{if not $v}}{{$v}}{{else}}{{$v | base64decode}}{{end}}{{"\n"}}{{end}}' get secret <name> 
    ```

=== "Output"
    ```bash

    ```    
  
