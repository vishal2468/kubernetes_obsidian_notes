[[Pods]] is **the smallest execution unit in Kubernetes**.

[[replicaset]]  ensures that a predefined number of pods always run

[[deployments]] tells Kubernetes how to create or modify instances of the pods that hold a containerised application.

[[services]] is a method for exposing a network application that is running as one or more Pods in your cluster.

[[namespace]] provides a mechanism for isolating groups of object within a single cluster.

[[label]]  are key/value pairs that are attached to objects such as Pods

[[selectors]]  the client/user can identify a set of objects

[[taint]] and [[tolerations]] work together to ensure that pods are not scheduled onto inappropriate nodes

[[Node-affinity]] set of rules used by the scheduler to determine where a pod can be placed

[[request]] and [[limit]] The kubelet also reserves at least the _request_amount of that system resource specifically for that container to use. A [[container]] is not allowed to use more than its resource `limit`.

[[daemonset]] ensures that all (or some) Nodes run a copy of a Pod.

[[staticpods]]  are managed directly by the [[kubelet]] daemon on a specific node, without the [[API server]] observing them

[[Schedulers]] is a control plane process which assigns Pods to Nodes. 
84