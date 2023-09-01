#storage 
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: myclaim
spec:
  accessModes:
    - ReadWriteOnce
  resources:
	  requests:
		  storage: 500Mi

```


using [[PersistentVolumeClaim]] in a pod 
it is defined in [[spec]].[[Volumes]] section.
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
  - image: registry.k8s.io/test-webserver
    name: test-container
    volumeMounts:
    - mountPath: /cache
      name: mypd
  volumes:
  - name: mypd
    persistentVolumeClaim:
	    claimName: myclaim
```

