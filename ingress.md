# Ingress

```yaml
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
  name: nginx
spec:
  tls:
  - secretName: shubhamtatvamasi-tls
    hosts:
      - parity.shubhamtatvamasi.com
      - prometheus.shubhamtatvamasi.com
  rules:
  - host: prometheus.shubhamtatvamasi.com
    http:
      paths:
      - path: /
        backend:
          serviceName: prometheus-alertmanager
          servicePort: http
```
