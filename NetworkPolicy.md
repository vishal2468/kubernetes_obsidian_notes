Network policies are implemented by the [network plugin](https://kubernetes.io/docs/concepts/extend-kubernetes/compute-storage-net/network-plugins/). To use network policies, you must be using a networking solution which supports NetworkPolicy. Creating a NetworkPolicy resource without a controller that implements it will have no effect.

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: test-network-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      role: db
  policyTypes:
    - Ingress
    - Egress
  ingress:
    - from:
        - ipBlock:
            cidr: 172.17.0.0/16
            except:
              - 172.17.1.0/24
        - namespaceSelector:
            matchLabels:
              project: myproject
        - podSelector:
            matchLabels:
              role: frontend
      ports:
        - protocol: TCP
          port: 6379
  egress:
    - to:
        - ipBlock:
            cidr: 10.0.0.0/24
      ports:
        - protocol: TCP
          port: 5978
```

There are four kinds of [[selectors]] that can be specified in an `ingress` `from` section or `egress` `to` section:
- **podSelector**
- **namespaceSelector**
- **namespaceSelector** _and_ **podSelector**
- **ipBlock**

Network policies in Kubernetes use specific types of selectors, such as `podSelector` and `namespaceSelector`, to provide fine-grained control over network traffic between pods. The use of these specific selectors instead of common selectors (like label selectors) is driven by the need to enforce security and isolation in a flexible and targeted manner.