## new operator

=== "Command"
    ```bash
    operator-sdk new memcached-operator --api-version=cache.example.com/v1alpha1 --kind=Memcached --type=ansible
    ```

=== "Output"
    ```bash
    INFO[0000] Creating new Ansible operator 'memcached-operator'.
    INFO[0000] Created deploy/service_account.yaml
    INFO[0000] Created deploy/role.yaml
    INFO[0000] Created deploy/role_binding.yaml
    INFO[0000] Created deploy/crds/cache.example.com_v1alpha1_memcached_cr.yaml
    INFO[0000] Created build/Dockerfile
    INFO[0000] Created roles/memcached/README.md
    INFO[0000] Created roles/memcached/meta/main.yml
    INFO[0000] Created roles/memcached/files/.placeholder
    INFO[0000] Created roles/memcached/templates/.placeholder
    INFO[0000] Created roles/memcached/vars/main.yml
    INFO[0000] Created molecule/test-local/converge.yml
    INFO[0000] Created roles/memcached/defaults/main.yml
    INFO[0000] Created roles/memcached/tasks/main.yml
    INFO[0000] Created molecule/default/molecule.yml
    INFO[0000] Created molecule/default/prepare.yml
    INFO[0000] Created molecule/default/converge.yml
    INFO[0000] Created molecule/default/verify.yml
    INFO[0000] Created roles/memcached/handlers/main.yml
    INFO[0000] Created watches.yaml
    INFO[0000] Created deploy/operator.yaml
    INFO[0000] Created .travis.yml
    INFO[0000] Created requirements.yml
    INFO[0000] Created molecule/test-local/molecule.yml
    INFO[0000] Created molecule/test-local/prepare.yml
    INFO[0000] Created molecule/test-local/verify.yml
    INFO[0000] Created molecule/cluster/molecule.yml
    INFO[0000] Created molecule/cluster/create.yml
    INFO[0000] Created molecule/cluster/prepare.yml
    INFO[0000] Created molecule/cluster/converge.yml
    INFO[0000] Created molecule/cluster/verify.yml
    INFO[0000] Created molecule/cluster/destroy.yml
    INFO[0000] Created molecule/templates/operator.yaml.j2
    INFO[0000] Generated CustomResourceDefinition manifests.
    INFO[0000] Project creation complete.
    ```
