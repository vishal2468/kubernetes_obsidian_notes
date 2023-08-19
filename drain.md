#cluster-maintenance 
to safely evict all of your pods from a _node_ before you perform maintenance on the node.

Drain runs the [[cordon]] command before evicting the pods from the node.