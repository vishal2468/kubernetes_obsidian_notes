get deployments 
	[[kubectl]] [[get]] deployments
create deployment using [[defination-file]]
	[[kubectl]] [[create]] -f [[defination-file]] 
	[[kubectl]] create deployment <deployment-name> --image <image-name> --replicas <[[count]]>
create deployment in a namespace
	[[kubectl]] create deployment <deployment-name> --image <image-name> --namespace <namespace-name>
delete deployments
	[[kubectl]] [[delete]] deployments <deployment-name>
edit a deployment 
	[[kubectl]] apply -f [[defination-file]]
Undo deployments
	[[kubelet]] rollout undo deployment/<deployment-name>
get rollout status 
	[[kubectl]] rollout status deployment/<deployment-name>
get rollout history 
	[[kubectl]] rollout history deployment/<deployment-name>
	
Deployment Strategies
	[[rollingUpdates]] allow Deployments' update to take place with zero downtime by incrementally updating Pods instances with new ones.
	[[recreate]]  terminates all the pods and replaces them with the new version.






	
	