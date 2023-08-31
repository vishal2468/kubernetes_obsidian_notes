#security
[[Authentication]] means validating the identity of who or what is issuing the request.

[[Authorization]]  in Kubernetes _verifies whether a certain action (such as_ “list pods” or “create a secret”) is allowed by a certain user or application.

[[SecurityContext]] defines privilege and access control settings for a Pod or Container.


The main difference between Security Context and Service Account lies in their purposes and scope:

- **Purpose:**
    - Security Context is about defining security-related settings within the pod or container to enhance isolation and control over how processes run.
    - Service Account is about establishing an identity for the pod/container to interact with the Kubernetes API and access cluster resources.
- **Scope:**
    
    - Security Context is applied to a specific pod or container, focusing on their runtime behavior and security settings.
    - Service Account is associated with the entire pod and defines how the pod's containers interact with the Kubernetes API server and resources.