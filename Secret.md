list secrets 
	[[kubelet]] [[get]] secrets 

describe secrets
	[[kubectl]] [[describe]] secrets

describe secrets with <key-value>
	[[kubelet]] describe secrets -o yaml
	
Create secret
	[[kubelet]] create secret generic <secret-name> --from-literal=<key>=<value>

	[[kubelet]] create secret generic <secret-name> 
		--from-literal=<key>=<value>
		--from-literal=<key>=<value>
		--from-literal=<key>=<value>

create secret from a file 
	[[kubelet]] [[create]] secret generic <secret-name>
		--from-file=<path-to-file>

create a secret using [[defination-file]]

	[[kubelet]] [[create]] -f [[defination-file]]

Secret [[defination-file]]
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: bootstrap-token-5emitj
  namespace: kube-system
type: bootstrap.kubernetes.io/token
data:
  auth-extra-groups: c3lzdGVtOmJvb3RzdHJhcHBlcnM6a3ViZWFkbTpkZWZhdWx0LW5vZGUtdG9rZW4=
  expiration: MjAyMC0wOS0xM1QwNDozOToxMFo=
  token-id: NWVtaXRq
```
	
use a [[secret]] in [[pods]] using [[envFrom]]
```yaml
spec:
  containers:
    - name: test-container
      image: registry.k8s.io/busybox
      command: [ "/bin/sh", "-c", "env" ]
      envFrom:
      - secretRef:
		 name: app-config
```

use a [[Secret]] in [[pods]] using [[env]]
```yaml
spec:
  containers:
  - env:
    - name: APP_COLOR
      valueFrom:
       secretKeyRef:
         name: app-config
         key: APP_COLOR
```




