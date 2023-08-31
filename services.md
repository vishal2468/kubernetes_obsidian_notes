Service types 
	[[ClusterIP]]  services expose pods to internal network traffic.
	[[NodePort]]  services are useful for exposing pods to external traffic where clients have network access to the Kubernetes nodes.
	[[LoadBalancer]] services are the best choice when pods need to be exposed to external clients via a predictable URL.
get services list
	[[kubectl]] [[get]] services
describe a service
	[[kubectl]] [[describe]] service <service-name>
create a service using [[defination-file]]
	[[kubectl]] create -f <defination-file>
delete a service
	[[kubectl]] [[delete]] service <service-name>







