`NodePort` services expose pods internally the same way a [[ClusterIP]] service does. In addition, a `NodePort` service allows external clients to access pods via network ports opened on the Kubernetes [[node]].

```yaml
apiVersion: v1 
kind: Service 
metadata: 
	name: my-service 
spec: 
	type: NodePort 
	selector: 
		app: web 
	ports: 
		- protocol: TCP 
		  port: 80 
		  targetPort: 8080 
		  nodePort: 30007
```

The YAML below defines a `NodePort` service that directs traffic on port 30007 on each node (defined by the `nodePort` property) to port 8080 (defined by the `targetPort` property) on any pods with the label `app` set to `web`.


