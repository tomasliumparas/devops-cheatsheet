## Role tasks template

=== "defaults/main.yml"

    ```yaml
    os_packages: []
    pip_packages: []
    ```

=== "tasks/main.yml"

    ```yaml
    ---
    # tasks file for example

    - name: Example prerequisites
      include: prerequisites.yml
      tags:
        - example
        - prerequisites

    - name: Example installation
      include: installation.yml
      tags:
        - example
        - installation

    - name: Example volume management
      include: volumes.yml
      tags:
        - example
        - volumes

    # CAUTION - Will REMOVE changes made and data
    - name: Example uninstallation
      include: uninstallation.yml
      tags:
        - example
        - uninstallation
      when: uninstall_role|default(false)
    ```

=== "prerequisites.yml"

    ```yaml
    ---
    # tasks file for example

    - name: Install additional OS packages
      package:
        name: "{{ item }}"
        state: present
      with_items: "{{ os_packages }}"
      loop_control:
        label: "PACKAGE: {{ item }}"

    - name: Install additional pip packages
      pip:
        name: "{{ pip_packages }}"
        state: latest
    ```

## Reject items w\ empty key in the list

=== "Snippet"

    ```yaml
    rejectattr('nodes', 'none')
    ```

=== "Task"

    ```yaml
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

## Special tags never

=== "Task"

    ```yaml
    - debug: msg='{{ showmevar}}'
      tags: [ 'never', 'debug' ]
    ```
