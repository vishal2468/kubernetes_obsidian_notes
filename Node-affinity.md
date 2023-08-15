nodes with [[Label]] are required for matching 

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

