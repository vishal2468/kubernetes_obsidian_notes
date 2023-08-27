#security 
```csv
password123 , user123 , u001 , group1 
```
The file has 3 columns password , user name , user id , group (optional)

we pass the file as an option to [[kube-apiserver]] [[kube-apiserver.service]] file
```
--basic-auth-file = user-details.csv
```

If we setup the server using [[kubeadm]] tool then we can pass the user-details file in the [[kube-apiserver]] pod defination file.


Now , the user while accessing the [[kube-apiserver]] , send the password and username in the curl command 
```curl
curl -k -v https://master-node-ip:6443/api/v1/pods -u "username1:password1"
```
