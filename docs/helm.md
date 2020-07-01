## Export yaml files locally

``` bash tab="Command"
export CHART=example-app
helm template --output-dir manifests --release-name $CHART-f values.yaml .
```

```bash tab="Output"
wrote manifests/cortex/templates/podsecuritypolicy.yaml
wrote manifests/cortex/templates/serviceaccount.yaml
wrote manifests/cortex/templates/secret.yaml
wrote manifests/cortex/templates/nginx-config.yaml
wrote manifests/cortex/templates/role.yaml
wrote manifests/cortex/templates/rolebinding.yaml
wrote manifests/cortex/templates/alertmanager-svc.yaml
wrote manifests/cortex/templates/configs-svc.yaml
wrote manifests/cortex/templates/distributor-svc.yaml
wrote manifests/cortex/templates/ingester-svc.yaml
wrote manifests/cortex/templates/nginx-svc.yaml
...
```
