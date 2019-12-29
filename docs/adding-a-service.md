# Adding a Service

1. namespace

```

```

1. deployment

  ```
  ---
  apiVersion: apps/v1
  kind: Deployment
  metadata:
    name: httpbin
  spec:
    replicas: 1
    selector:
      matchLabels:
        app: httpbin
        version: v1
    template:
      metadata:
        labels:
          app: httpbin
          version: v1
      spec:
        serviceAccountName: httpbin
        containers:
        - image: docker.io/kennethreitz/httpbin
          imagePullPolicy: IfNotPresent
          name: httpbin
          ports:
          - containerPort: 80
  ---
  ```

2. service

  ```
  ---
  apiVersion: v1
  kind: Service
  metadata:
    name: httpbin
    labels:
      app: httpbin
  spec:
    type: ClusterIP
    ports:
      - protocol: TCP
        name: web
        port: 80
    selector:
      app: httpbin
  ---

  ```

3. ingress-route