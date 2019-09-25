# Kubernetes
試したサンプルとかを置いとくリポジトリ

## Tools

### kubectl

```
$ kubectl get nodes
$ kubectl get pods

$ kubectl apply -f pod.yaml
$ kubectl describe pods ${POD_NAME}
```

### kubectx

```
$ kubectx
```

### stern

```
$ stern ${POD_NAME}
```