### pod-test.yaml

```bash

$ kubectl create -f sample/pod-test.yaml
$ kubectl get pods
$ kubectl get -f sample/pod-test.yaml
$ kubectl get pod-test
$ kubectl delete -f sample/pod-test.yaml

```

### namespace

```bash

$ kubectl create namespace test-ns
$ kubectl get ns
$ kubectl delete ns test-ns

$ kubectl create ns test-ns --dry-run=client -o yaml > test-ns.yaml

```
