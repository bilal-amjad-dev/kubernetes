
**Create a namespace**

```bash
kubectl create namespace dev
```


**To limit resources in a namespace, create a resource quota**

```bash
apiVersion: v1
kind: ResourceQuota
metadata:
  name: compute-quota
  namespace: dev
spec:
  hard:
    pods: "10"
    requests.cpu: "4"
    requests.memory: 5Gi
    limits.cpu: "10"
    limits.memory: 10Gi
```

```bash
$ kubectl create -f compute-quota.yaml
```


