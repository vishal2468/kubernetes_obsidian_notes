#security 
```json
{
	"apiVersion": "abac.authorization.kubernetes.io/v1beta1",
	"kind": "Policy",
	"spec": {
			"user": "alice",
			"namespace": "*",
			"resource": "*", 
			"apiGroup": "*"
		}
}
```

we must pass this file to [[kube-apiserver]] and also restart the server every time changes are made to this file.
the following flags need to be set for [[kube-apiserver]]

```
--authorization-policy-file=SOME_FILENAME
--authorization-mode=ABAC
```