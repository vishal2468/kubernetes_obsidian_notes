[[Kubernetes]] can manage service accounts.

	[[kubectl]] get serviceaccount 
	kubectl create serviceaccount <service-acc-name>
	kubectl describe serviceaccount <service-acc-name>

Service account has [[secret]] token that is used for its authentication.It is mounted at some specific location.

Every [[Pods]] that is generated has a default service account generated for it.
We can specify our own service account information in pod [[defination-file]].


