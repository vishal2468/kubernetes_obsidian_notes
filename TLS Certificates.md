#security 
Server Certificates : Configured on servers
Client Certificates : Configured on clients
Root Certificate : Configured on CA

(certificate) public key extensions: \*.crt , \*.pem
private key extensions: \*.key \*-key.pem

Generate certificate 
```
openssl genrsa -out <new-key-file-name>.key 2048
```

Certificate signing request 
```
openssl req -new -key <new-key-file-name>.key \
-subj "/CN=<COMMON-NAME> /O=<USER-ROLE>" \
-out <new-key-file-name>.csr
```

Sign Certificates 
```
openssl x509 -req -in <new-key-file-name>.csr \
-CA <certificate-authority>.crt 
-CAkey ca.key -out admin.crt
```

these certificates can be used with the curl request to authenticate oneself 
```
curl -k -v https://master-node-ip:6443/api/v1/pods \
--key admin.key --cert=admin.crt
-cacert ca.crt
```

View the certificate
```
openssl x509 -in /etc/kubernetes/pki/<certificate-file-name>.crt -text
```

or we could move all these paramenters in a configuration file [[kube-config.yaml]] . This is what most of the client use.


- [[etcd]] certificate files are specified in various etcd.yaml definition file.
- for [[kube-apiserver]] we pass the file as an option to [[kube-apiserver.service]] file
- [[kubelet]] certificates are tagged in kubelet-config.yaml.


[[Kubernetes]] has builtin tool for certificates management
it resides in [[Controller-manager]] and has two parts 
- csr approving 
- csr signing
We create a csr string using the commands mentioned above 
and then create a [[CertificateSigningRequest]] in a [[defination-file]]
We can then use [[kubectl]] commands for certificates signing(approval) .





