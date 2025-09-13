
- Another way to create a namespace

```bash
kubectl create namespace dev
```


- If you want to make sure that this pod gets you created in the dev env all the time, even if you don't specify in the command line, you can move the --namespace definition into the pod-definition file.
```bash
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  namespace: dev
  labels:
     app: myapp
     type: front-end
spec:
  containers:
  - name: nginx-container
    image: nginx
```


- To limit resources in a namespace, create a resource quota.
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


