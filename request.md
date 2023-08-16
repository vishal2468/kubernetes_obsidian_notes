```yaml
spec:
  containers:
  - name: app
    image: images.my-company.example/app:v4
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
  - name: log-aggregator
    image: images.my-company.example/log-aggregator:v6
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
```
Request is defined under the [[spec]] in [[defination-file]]
- [[spec]].containers[].[[resources]].requests.cpu
- [[spec]].containers[].resources.requests.memory
- [[spec]].containers[].resources.requests.ephemeral-storage