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