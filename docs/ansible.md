## Reject items w\ empty key in the list

``` tab="Snippet"
rejectattr('nodes', 'none')
```

```bash tab="Task"
- name: Filter empty
  set_fact:
    clusters: "{{ clusterList | rejectattr('nodes', 'none') | list }}"
  delegate_to: localhost
  vars:
    clusters:
      - cluster: cl1
        nodes: null
      - cluster: cl2
        nodes:
          - node1
          - node2
          - node3
```
