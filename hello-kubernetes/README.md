## Make docker image

```
$ docker build -t hello-node:1.0 .
```

## docker run from gcr's sample

```
$ docker container run -p 9000:8080 gcr.io/google-samples/hello-app:1.0

$ curl http://localhost:9000/
```

## make deployment

```
$ kubectl create deployment hello-node --image=gcr.io/google-samples/hello-app:1.0

$ kubectl get deployments
```