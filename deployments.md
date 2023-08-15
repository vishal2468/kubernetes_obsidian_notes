get deployments 
	[[kubectl]] [[get]] deployments
create deployment using [[defination-file]]
	[[kubectl]] [[create]] -f [[defination-file]] 
	[[kubectl]] create deployment <deployment-name> --image <image-name> --replicas <[[count]]>
create deployment in a namespace
	[[kubectl]] create deployment <deployment-name> --image <image-name> --namespace <namespace-name>
delete deployments
	[[kubectl]] [[delete]] deployments <deployment-name>

	
	