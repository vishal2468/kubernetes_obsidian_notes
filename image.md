docker.io/library/nginx
`registry/{user or account}/{image or repo}`

docker.io is the registry.
library is the default account name that is used if no account name is specified.
nginx is the image name.


We can have private registries to store our image

login to a private repo
	docker login <Private-repo-id>

Create a pod from a private repository image
	Create a secret of type docker-registry and name regcred
		`kubectl create secret docker-registry regcred \
		--docker-server= 
		--docker-username= 
		--docker-password= 
		--docker-email= `

	define the secret in pods defination-file in [[imagePullSecrets]] section in [[spec]]