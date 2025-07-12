# Forward
Creates a service that forwards http/s traffic to an external endpoint / to external endpoints.

## Example
Forward traffic to 192.168.0.100

### values.yaml
```yaml
addresses:
  - ip: 192.168.0.100
```

### Installation
```sh
helm repo add homelab https://github.com/05Paul/homelab-charts
helm install forward homelab/forward -n forward --create-namespace -f values.yaml
```

