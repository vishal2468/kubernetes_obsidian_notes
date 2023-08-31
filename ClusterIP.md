```yaml
apiVersion: v1
kind: Service 
metadata: name: my-service 
spec: 
	type: ClusterIP 
	selector: 
		app: web 
	ports: 
		 -  protocol: TCP 
			port: 80 
			targetPort: 8080
```

The YAML below defines a service of type `ClusterIP` that directs traffic on port 80 (defined by the `port` property) to port 8080 (defined by the `targetPort` property) on any pods with the label `app` set to `web` (defined by the `selector` property)