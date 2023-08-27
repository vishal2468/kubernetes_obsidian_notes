#security 
```
sunaiujuajushygsdfhaHSuhahsuhahsuhasuahs , user123 , u001 , group1 
```
The file has 3 columns token , user name , user id , group (optional)

we pass the file as an option to [[kube-apiserver]] [[kube-apiserver.service]] file
```
--token-auth-file = user-details.csv
```

If we setup the server using [[kubeadm]] tool then we can pass the user-details file in the [[kube-apiserver]] pod defination file.

Now , the user while accessing the [[kube-apiserver]] , send the password and username in the curl command 

```curl
curl -k -v https://master-node-ip:6443/api/v1/pods -header "Autherization: Bearer njajnsjiajsjdijdiwidjsidjsi"
```