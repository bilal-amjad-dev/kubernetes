
So far in this course we have created Objects such as PODs, Deployments and Services in our cluster. Whatever we have been doing we have been doing in a NAMESPACE.

- This namespace is the default namespace in kubernetes. It is automatically created when kubernetes is setup initially.


- To view pods in all namespaces
```bash
kubectl get pods --all-namespaces
```


- By default, we will be in a default namespace. To switch to a particular namespace permenently run the below command.
```bash
kubectl config set-context $(kubectl config current-context) --namespace=dev
```
