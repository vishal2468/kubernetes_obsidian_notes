
	[[env]] allows you to set environment variables for a [[container]], specifying a value directly for each variable that you name.

	[[envFrom]] allows you to set environment variables for a container by referencing either a [[ConfigMap]] or a [[Secret]].

	[[envFrom]] to define all of the ConfigMap's data as container environment variables. The key from the ConfigMap becomes the environment variable name in the Pod.