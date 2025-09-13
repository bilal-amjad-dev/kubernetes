

Create a new deployment with the nginx image.

```bash
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-first-deployment # A name for your deployment
spec:
  replicas: 1 # How many copies (pods) of your application you want to run
  selector:
    matchLabels:
      app: my-app # This matches the labels on the pods this deployment manages
  template:
    metadata:
      labels:
        app: my-app # Labels for the pods created by this deployment
    spec:
      containers:
      - name: my-container # A name for the container inside the pod
        image: nginx:latest # The Docker image to use for your application (e.g., Nginx web server)
        ports:
        - containerPort: 80 # The port your application listens on inside the container
```
