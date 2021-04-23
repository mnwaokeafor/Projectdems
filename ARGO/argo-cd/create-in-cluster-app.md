CLI

argocd app create --name test \
--repo https://github.com/mnwaokeafor/ARGO \
--dest-server https://kubernetes.default.svc \
--dest-namespace myke --path kubernetes
YAML

apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test
  namespace: myke
spec:
  project: default
  source:
    repoURL: https://github.com/mnwaokeafor/ARGO.git
    targetRevision: HEAD
    path: argo/example-app
  destination:
    server: https://kubernetes.default.svc
    namespace: myke