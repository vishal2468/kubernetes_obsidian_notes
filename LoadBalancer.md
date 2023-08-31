`LoadBalancer` services expose pods internally the same way a [[NodePort]] service does. In addition, `LoadBalancer` services create external network infrastructure to direct network requests to pods in the cluster. On cloud platforms, like Azure, AWS, and GCP, the external load balancer is typically provided by one of the cloud provider's existing load balancer services.

```yaml
apiVersion: v1
kind: Service 
metadata: name: my-service 
spec: 
	type: LoadBalancer 
	selector: 
		app: web 
	ports: 
		 -  protocol: TCP 
			port: 80 
			targetPort: 8080
```


The YAML below defines a `LoadBalancer` service that directs traffic from port 80 (defined by the `port` property) on a public load balancer and internal service to port 8080 (defined by the `targetPort` property) on any pods with the label `app` set to `web`

