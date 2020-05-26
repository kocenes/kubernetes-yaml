# Kubernetes deployment example

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  labels:
    app: nginx
  name: nginx
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  strategy: {}
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - command:
        - sleep
        - "1000"
        image: nginx
        name: nginx
        ports:
        - containerPort: 8080
        resources:
          limits:
            memory: 20Mi
          requests:
            memory: 15Mi
```