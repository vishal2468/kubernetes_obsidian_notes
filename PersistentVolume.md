So that user may not have to configure storage for each pod, the administrator can create persistent volumes and the users can use the volumes from the pool of volumes that has been made available to them by the admin.
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv0003
spec:
  capacity:
    storage: 5Gi
  accessModes:
    - ReadWriteOnce
  awsElasticBlockStore: 
	volumeID: <volume-id>
	fsType: ext4
```

it is bound to [[PersistentVolumeClaim]]