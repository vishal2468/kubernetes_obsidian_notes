2 ways 
- quering the [[kube-apiserver]] for all the resource groups and backing them up.
- take a snapshot of the [[etcd]] db.
for managed k8s cluster , we may not have access to etcd and in that case the 1st method is preferred.


ETCD method

backup
```
ETCDCTL_API=3 etcdctl --endpoints=https://[127.0.0.1]:2379 \
--cacert=/etc/kubernetes/pki/etcd/ca.crt \
--cert=/etc/kubernetes/pki/etcd/server.crt \
--key=/etc/kubernetes/pki/etcd/server.key \
snapshot save /opt/snapshot-pre-boot.db
```
restore
```
ETCDCTL_API=3 etcdctl snapshot restore --data-dir /var/lib/etcd-from-backup  /opt/snapshot-pre-boot.db
```

we will also have to make changes to the volume path  in etcd [[defination-file]] to point to this restored data


