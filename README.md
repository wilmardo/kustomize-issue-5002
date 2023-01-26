### Demo for issue #5003

It complains about a missing spec/namespace
```console
# kustomize build demo1/
Error: replace operation does not apply: doc is missing path: /spec/namespace: missing value
```

But when rendering the base this is present
```console
# kustomize build base/
apiVersion: v1
kind: Endpoints
metadata:
  name: test-endpoint
  namespace: placeholder
subsets:
- addresses:
  - ip: 1.1.1.1
  ports:
  - port: 100
    protocol: TCP
```