

**ClusterIP:**

In Kubernetes, the ClusterIP Service is used for Pod-to-Pod communication within the same cluster. This means that a client running outside of the cluster, such as a user accessing an application over the internet, cannot directly access a ClusterIP Service.


**NodePort:**

The NodePort Service provides a way to expose your application to external clients. An external client is anyone who is trying to access your application from outside of the Kubernetes cluster.
vice YAML has a `selector` field under its `spec`. The Service uses this selector (`app: my-nginx-app`)

- This is how Kubernetes Services know which Pods to send traffic to. The selector is the "glue" that connects a Service to its corresponding Pods.
