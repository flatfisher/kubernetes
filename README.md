# Kubernetes
試したサンプルとかを置いとくリポジトリ

## Tools

### kubectl

```
$ kubectl get nodes
$ kubectl get pods

$ kubectl apply -f pod.yaml
$ kubectl describe pods ${POD_NAME}

$ kubectl delete -f manifests/pod.yaml

$ kubectl port-forward introduction-web 8080:80
```

### kubectx

```
$ kubectx
```

### stern

```
$ stern ${POD_NAME}
```

### dashboard

- https://github.com/kubernetes/dashboard
- https://github.com/kubernetes/dashboard/releases

```
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0-beta4/aio/deploy/recommended.yaml

$ kubectl get deployments,replicasets,pods,service --all-namespaces -o wide --selector=k8s-app=kubernetes-dashboard

//After Running
$ kubectl proxy

$ http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/

//Delete
kubectl get secret,sa,role,rolebinding,services,deployments --namespace=kube-system | grep dashboard

kubectl delete deployment kubernetes-dashboard --namespace=kube-system
kubectl delete service kubernetes-dashboard  --namespace=kube-system
kubectl delete role kubernetes-dashboard-minimal --namespace=kube-system
kubectl delete rolebinding kubernetes-dashboard-minimal --namespace=kube-system
kubectl delete sa kubernetes-dashboard --namespace=kube-system
kubectl delete secret kubernetes-dashboard-certs --namespace=kube-system
kubectl delete secret kubernetes-dashboard-key-holder --namespace=kube-system
```