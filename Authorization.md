	[[RBAC Authorization]] 
	[[ABAC Authorization]] defines an access control paradigm whereby access rights are granted to users through the use of policies which combine attributes together.
	[[Node Authorization]] is a special-purpose _authorization_ mode that specifically authorizes API requests made by kubelets.
	[[Webhook Mode]] Authorization is taken care by some 3rd party application.
	[[AlwaysAllow]]
	[[AlwaysDeny]]
	
	
We can specify multiple authorization modes in [[kube-apiserver]].
```
--authorization-mode=ABAC,RBAC
```
