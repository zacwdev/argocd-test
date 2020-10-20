
CLI
```
argocd app create --name test \
--repo https://github.com/zacwdev/argocd-test \
--dest-server https://kubernetes.default.svc \
--dest-namespace zacw --path kubernetes
```

YAML

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test
  namespace: zacw
spec:
  project: default
  source:
    repoURL: https://github.com/zacwdev/argocd-test.git
    targetRevision: HEAD
    path: argo/example-app
  destination:
    server: https://kubernetes.default.svc
    namespace: zacw
```
