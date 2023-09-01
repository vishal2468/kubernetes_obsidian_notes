#security 
```yaml
spec:
  securityContext:
    runAsUser: 1000
```
it can be defined at container level or pod level



Capabilities can be defined only at pod level
With [Linux capabilities](https://man7.org/linux/man-pages/man7/capabilities.7.html), you can grant certain privileges to a process without granting all the privileges of the root user.
```yaml
spec:
  containers:
  - name: sec-ctx-4
    image: gcr.io/google-samples/node-hello:1.0
    securityContext:
		runAsUser: 1000
	    capabilities:
	        add: ["NET_ADMIN", "SYS_TIME"]
```

The main difference between Security Context and [[Service Accounts]] lies in their purposes and scope:

- **Purpose:**
    - Security Context is about defining security-related settings within the pod or container to enhance isolation and control over how processes run.
    - Service Account is about establishing an identity for the pod/container to interact with the Kubernetes API and access cluster resources.
- **Scope:**
    
    - Security Context is applied to a specific pod or container, focusing on their runtime behavior and security settings.
    - Service Account is associated with the entire pod and defines how the pod's containers interact with the Kubernetes API server and resources.