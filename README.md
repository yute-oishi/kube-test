### run

```bash

$ kubectl run nginx --image=nginx

```

### pod-test.yaml

```bash

$ kubectl apply -f sample/pod-test.yaml
$ kubectl get pods
$ kubectl get -f sample/pod-test.yaml
$ kubectl get pod-test
$ kubectl delete -f sample/pod-test.yaml

```

### namespace-test.yaml

```bash

$ kubectl create namespace test-ns
$ kubectl get ns
$ kubectl delete ns test-ns
$ kubectl create ns test-ns --dry-run=client -o yaml > test-ns.yaml

$ kubectl apply -f .\sample\namespace-test.yaml
$ kubectl delete -f .\sample\namespace-test.yaml
```

### replicaset-test.yaml

```bash

$ kubectl apply -f .\sample\replicaset-test.yaml
$ kubectl get replicaset
$ kubectl get pods

```

### deployment-test.yaml

```bash

$ kubectl apply -f .\sample\deployment-test.yaml
$ kubectl get deploy
$ kubectl get rs
$ kubectl get pods

$ kubectl rollout history deploy
$ kubectl rollout undo deploy --to-revision=1

```

### configmap

```bash
# by env
$ kubectl apply -f .\sample\configmap-env.yaml
$ kubectl logs test-pod
$ kubectl delete cm test-config
$ kubectl delete pod test-pod

# by file (volume)
$ kubectl apply -f .\sample\configmap-file.yaml
$ kubectl exec -it test-pod busybox sh
$ cat datadir/data.csv
$ exit
$ kubectl delete cm test-file
$ kubectl delete pod test-pod

```

### secret

```bash
# by env
$ kubectl apply -f sample/secret-env.yaml
$ kubectl get secrets
$ kubectl logs test-pod
$ kubectl delete secret mysecret
$ kubectl delete pod test-pod

# by file (volume)
$ kubectl apply -f .\sample\secret-file.yaml
$ kubectl create secret generic my --from-file=data.csv=./sample/secret-data.csv --dry-run=client -o yaml
$ kubectl exec -it test-pod busybox sh
$ cat datadir/data.csv
$ exit
$ kubectl delete secret mysecret
$ kubectl delete pod test-pod

```

### service

```bash

$ kubectl apply -f sample/service.yaml
$ kubectl get services
$ kubectl get deploy
$ kubectl get pods --show-labels
$ kubectl get endpoints

$ kubectl port-forward svc/nginx 8080:80
# watch
$ kubectl logs nginx-6c9fd56bbc-bxhbn -f
# access to http://localhost:8080
```
