
**Note:** *For the Service to connect to the Pod, you need to add a label to the Pod's metadata.*

Here's an updated version of the Pod YAML that includes the required label.


`vi pod.yaml`
```bash
apiVersion: v1
kind: Pod
metadata:
  name: my-nginx-pod
  labels:
    app: my-nginx-app
spec:
  containers:
  - name: nginx-container
    image: nginx:latest
    ports:
    - containerPort: 80
```


`vi service.yaml`:
```bash
apiVersion: v1
kind: Service
metadata:
  name: my-nginx-service
spec:
  selector:
    app: my-nginx-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: NodePort
```

```bash
kubectl apply -f pod.yaml
```

```bash
kubectl apply -f service.yaml
```


- The Pod YAML has a `labels` field under its `metadata`. In the example, this is `app: my-nginx-app`.

- The Service YAML has a `selector` field under its `spec`. The Service uses this selector (`app: my-nginx-app`)

- This is how Kubernetes Services know which Pods to send traffic to. The selector is the "glue" that connects a Service to its corresponding Pods.
