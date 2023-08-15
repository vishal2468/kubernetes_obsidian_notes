Get pods list
	[[kubectl]] [[get]] pods
Create a pod from a [[image]]
	[[kubectl]] [[run]] <pod-name> --image <image-name>
Create a pod using a [[defination-file]]
	[[kubectl]] [[create]] -f <defination-file.yaml>
Describe a pod
	[[kubectl]] [[describe]] pod <pod-name>
Delete a pod
	[[kubectl]] [[delete]] pod <pod-name>
Get pods in a [[namespace]]
	[[kubectl]] get pods --namespace <namespace-name>
Get all pods in all [[namespace]]
	[[kubectl]] get pods -A
Scheduling 
	Mannual
	Through Schedulers
