[[ConfigMap]] [[defination-file]] 
```yaml
apiVersion: v1
data:
  APP_OTHER: disregard
  APP_COLOR: darkblue
kind: ConfigMap
metadata:
  name: webapp-config-map
```

use a [[configmap]] in [[pods]] using [[env]]
```yaml
spec:
  containers:
  - env:
    - name: APP_COLOR
      valueFrom:
       configMapKeyRef:
         name: webapp-config-map
         key: APP_COLOR
```

use a [[configmap]] in [[pods]] using [[envFrom]]
```yaml
spec:
  containers:
    - name: test-container
      image: registry.k8s.io/busybox
      command: [ "/bin/sh", "-c", "env" ]
      envFrom:
      - configMapRef:
          name: special-config
```

