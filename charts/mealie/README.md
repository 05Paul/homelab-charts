# Mealie
Deploys mealie

## Example

### values.yaml
```yaml
ingress:
  enabled: true
  className: nginx
  annotations: 
    cert-manager.io/cluster-issuer: letsencrypt-prod
  hosts:
    - host: mealie.example.com
      paths:
        - path: /
          pathType: ImplementationSpecific
  tls:
    - secretName: echo-tls
      hosts:
        - mealie.example.com
```

### Installation
```sh
helm repo add homelab https://github.com/05Paul/homelab-charts
helm install mealie homelab/mealie -n mealie --create-namespace -f values.yaml
```

