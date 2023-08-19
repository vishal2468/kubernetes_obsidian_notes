allowing you to constrain which [[node]] your [[Pods]] can be scheduled on based on node [[label]]

define affinity under [[spec]]
```yaml
spec:
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: disktype
            operator: In
            values:
            - ssd 
```

[[Node-affinity-type]]

