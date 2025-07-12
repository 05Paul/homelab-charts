# Forward-Ingress
Creates an ingress that forwards traffic to a given service

## Example
Forward traffic to echo service

### values.yaml
```yaml
service:
  name: echo
  port: 80

ingress:
  enabled: true
  className: nginx
  annotations: 
    cert-manager.io/cluster-issuer: letsencrypt-prod
  hosts:
    - host: echo.example.com
      paths:
        - path: /
          pathType: ImplementationSpecific
  tls:
    - secretName: echo-tls
      hosts:
        - echo.example.com
```

### Installation
```sh
helm repo add homelab https://github.com/05Paul/homelab-charts
helm install forward homelab/forward-ingress -n forward-ingress --create-namespace -f values.yaml
```

