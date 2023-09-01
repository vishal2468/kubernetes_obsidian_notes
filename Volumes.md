Mounting a volume in a pod
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: test-pd
spec:
  containers:
  - image: registry.k8s.io/test-webserver
    name: test-container
    volumeMounts:
    - mountPath: /cache
      name: cache-volume
  volumes:
  - name: cache-volume
    hostPath: 
	    path: /data
	    type: Directory
```

This method is not recommended for production as the data will be persisted in individual nodes.


Instead we use some cloud storage solutions.

```yaml
  volumes:
  - name: cache-volume
    awsElasticBlockStore: 
	    volumeID: <volume-id>
	    fsType: ext4
```