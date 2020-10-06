## Custom formatting

### Longer

=== "Command"

    ```
    docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Size}}\t{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
    ```

=== "Output"

    ```bash
    [root@docker03 tl]# docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Size}}\t{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
    CONTAINER ID        IMAGE                              SIZE                      CREATED             STATUS                    NAMES
    760868f422e7        hc-docs                            22kB (virtual 349MB)      34 hours ago        Up 13 minutes             hc-docs
    ed6472d97f53        mkdocs-example                     22kB (virtual 520MB)      34 hours ago        Up 13 minutes             mkdocs-example
    b9916d2c07a2        syncthing/syncthing:latest         0B (virtual 27.4MB)       2 days ago          Up 13 minutes (healthy)   syncthing
    7b8063ed5fc1        drone/drone-runner-docker:latest   0B (virtual 20.6MB)       2 weeks ago         Up 13 minutes             drone-runner
    cfa7878e62d7        drone/drone:latest                 0B (virtual 67.6MB)       2 weeks ago         Up 13 minutes             drone
    f8ce88dd8100        jordan/hubot-slack                 9.66MB (virtual 1.01GB)   4 months ago        Up 13 minutes             hubot
    ```

### Shorter

=== "Command"

    ```
    docker ps --format "table {{.ID}}\{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
    ```

=== "Output"

    ```bash
    [root@docker03]# docker ps --format "table {{.ID}}\t{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
    CONTAINER ID        CREATED             STATUS              NAMES
    b53823b515ef        3 days              Up 3 days           k8s_kube-flannel_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    c32dd9f2e6ef        3 days              Up 3 days           k8s_calico-node_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    70364abaed70        3 days              Up 3 days           k8s_fluent-bit_fluent-bit-qk8h6_logging_b368b8e4-0328-42c3-8550-6f15fedbf1a0_3
    1c75ea42b708        3 days              Up 3 days           k8s_POD_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    b12862c80b2b        3 days              Up 3 days           k8s_agent_cattle-node-agent-7kjjb_cattle-system_18f26dd8-3df4-4ec7-8a40-e5b99254a541_12
    91392f74d83d        3 days              Up 3 days           k8s_exporter-node_exporter-node-cluster-monitoring-jtlqt_cattle-prometheus_a25acec3-c54b-4aa4-8f6a-943f4113d675_12
    a9eb7bc837eb        3 days              Up 3 days           k8s_kube-api-auth_kube-api-auth-hjcz2_cattle-system_999e10bf-46b1-4c8f-8b03-60d9bfce998e_15
    5938100269fc        3 days              Up 3 days           k8s_POD_fluent-bit-qk8h6_logging_b368b8e4-0328-42c3-8550-6f15fedbf1a0_3
    43f63547da47        3 days              Up 3 days           k8s_POD_cattle-node-agent-7kjjb_cattle-system_18f26dd8-3df4-4ec7-8a40-e5b99254a541_12
    a37c47deca8f        3 days              Up 3 days           k8s_POD_exporter-node-cluster-monitoring-jtlqt_cattle-prometheus_a25acec3-c54b-4aa4-8f6a-943f4113d675_12
    561534e7c60e        3 days              Up 3 days           k8s_POD_kube-api-auth-hjcz2_cattle-system_999e10bf-46b1-4c8f-8b03-60d9bfce998e_15
    4122bd57cd44        2 weeks             Up 3 days           kube-apiserver
    da27fea870df        2 weeks             Up 3 days           etcd
    b8c921edc58b        4 months            Up 3 days           kube-proxy
    1e28bebce5ff        4 months            Up 3 days           kubelet
    54815c4c1a3e        4 months            Up 33 hours         kube-scheduler
    abaf23202d58        4 months            Up 33 hours         kube-controller-manager
    ```

### Shorter w/ failed containers
=== "Command"

    ```
    docker ps --format "table {{.ID}}\{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
    ```

=== "Output"

    ```bash
    [root@docker03]# docker ps -a  --format "table {{.ID}}\t{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
    CONTAINER ID        CREATED             STATUS                    NAMES
    b53823b515ef        3 days              Up 3 days                 k8s_kube-flannel_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    c32dd9f2e6ef        3 days              Up 3 days                 k8s_calico-node_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    5e7d8c255077        3 days              Exited (0) 3 days ago     k8s_flexvol-driver_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_0
    70364abaed70        3 days              Up 3 days                 k8s_fluent-bit_fluent-bit-qk8h6_logging_b368b8e4-0328-42c3-8550-6f15fedbf1a0_3
    9a95ba1b4060        3 days              Exited (0) 3 days ago     k8s_install-cni_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    1c75ea42b708        3 days              Up 3 days                 k8s_POD_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_15
    b12862c80b2b        3 days              Up 3 days                 k8s_agent_cattle-node-agent-7kjjb_cattle-system_18f26dd8-3df4-4ec7-8a40-e5b99254a541_12
    91392f74d83d        3 days              Up 3 days                 k8s_exporter-node_exporter-node-cluster-monitoring-jtlqt_cattle-prometheus_a25acec3-c54b-4aa4-8f6a-943f4113d675_12
    a9eb7bc837eb        3 days              Up 3 days                 k8s_kube-api-auth_kube-api-auth-hjcz2_cattle-system_999e10bf-46b1-4c8f-8b03-60d9bfce998e_15
    5938100269fc        3 days              Up 3 days                 k8s_POD_fluent-bit-qk8h6_logging_b368b8e4-0328-42c3-8550-6f15fedbf1a0_3
    43f63547da47        3 days              Up 3 days                 k8s_POD_cattle-node-agent-7kjjb_cattle-system_18f26dd8-3df4-4ec7-8a40-e5b99254a541_12
    a37c47deca8f        3 days              Up 3 days                 k8s_POD_exporter-node-cluster-monitoring-jtlqt_cattle-prometheus_a25acec3-c54b-4aa4-8f6a-943f4113d675_12
    561534e7c60e        3 days              Up 3 days                 k8s_POD_kube-api-auth-hjcz2_cattle-system_999e10bf-46b1-4c8f-8b03-60d9bfce998e_15
    c8217f650a16        4 days              Exited (0) 3 days ago     k8s_fluent-bit_fluent-bit-qk8h6_logging_b368b8e4-0328-42c3-8550-6f15fedbf1a0_2
    7a75b67521a1        4 days              Exited (137) 3 days ago   k8s_kube-flannel_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_14
    e6ed1db938df        4 days              Exited (0) 3 days ago     k8s_calico-node_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_14
    678c8242a12f        4 days              Exited (0) 3 days ago     k8s_POD_fluent-bit-qk8h6_logging_b368b8e4-0328-42c3-8550-6f15fedbf1a0_2
    f5db6771c4b1        4 days              Exited (2) 3 days ago     k8s_kube-api-auth_kube-api-auth-hjcz2_cattle-system_999e10bf-46b1-4c8f-8b03-60d9bfce998e_14
    83824972c208        4 days              Exited (2) 3 days ago     k8s_agent_cattle-node-agent-7kjjb_cattle-system_18f26dd8-3df4-4ec7-8a40-e5b99254a541_11
    7fb31ca14176        4 days              Exited (143) 3 days ago   k8s_exporter-node_exporter-node-cluster-monitoring-jtlqt_cattle-prometheus_a25acec3-c54b-4aa4-8f6a-943f4113d675_11
    0a9f7e21608c        4 days              Exited (0) 3 days ago     k8s_POD_canal-zr7nx_kube-system_886412c0-7fe4-44f5-8992-7326eb7404c2_14
    863f17b52802        4 days              Exited (0) 3 days ago     k8s_POD_kube-api-auth-hjcz2_cattle-system_999e10bf-46b1-4c8f-8b03-60d9bfce998e_14
    f6a8ef0e6de8        4 days              Exited (0) 3 days ago     k8s_POD_exporter-node-cluster-monitoring-jtlqt_cattle-prometheus_a25acec3-c54b-4aa4-8f6a-943f4113d675_11
    9649a21951bc        4 days              Exited (0) 3 days ago     k8s_POD_cattle-node-agent-7kjjb_cattle-system_18f26dd8-3df4-4ec7-8a40-e5b99254a541_11
    d5ac1a15ce9f        2 weeks             Exited (0) 2 weeks ago    k8s_rke-coredns-addon-pod_rke-coredns-addon-deploy-job-dhwv6_kube-system_5c17bcfe-6da8-44ec-9c3c-a565dcf63156_0
    e74fcf268361        2 weeks             Exited (0) 2 weeks ago    k8s_POD_rke-coredns-addon-deploy-job-dhwv6_kube-system_5c17bcfe-6da8-44ec-9c3c-a565dcf63156_0
    4122bd57cd44        2 weeks             Up 3 days                 kube-apiserver
    da27fea870df        2 weeks             Up 3 days                 etcd
    b8c921edc58b        4 months            Up 3 days                 kube-proxy
    1e28bebce5ff        4 months            Up 3 days                 kubelet
    54815c4c1a3e        4 months            Up 33 hours               kube-scheduler
    abaf23202d58        4 months            Up 33 hours               kube-controller-manager
    c77542fba600        4 months            Created                   service-sidekick
    87f23acc8622        4 months            Exited (0) 3 days ago     share-mnt
    ```

## Image digests

### Single image

=== "Command"

    ```
    docker image inspect --format='{{index .RepoDigests 0}}' alpine
    ```

=== "Output"

    ```bash
    Tomass-MacBook-Air:~ Tomas$ docker image inspect --format='{{index .RepoDigests 0}}' alpine
    alpine@sha256:185518070891758909c9f839cf4ca393ee977ac378609f700f60a771a2dfe321
    ```
