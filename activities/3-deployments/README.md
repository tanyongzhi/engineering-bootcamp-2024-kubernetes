# Deployments
Deployments help ensure that a certain number of pods are always running healthily.

## Demo
In the demo, we will be creating a deployment of an echo server container with 3 replicas.

## Challenge
Here is a sample deployment manifest from the Kubernetes documentation. You would have to change some fields in order to make it work: 
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```

Try to:
- Create a deployment of your Express app with 5 replicas
- List all pods. How many pods are there in total? What do you notice about the labels of these pods?
- Crash one of the pods (by sending a request to the `/crash` endpoint), what do you notice happens after that? How many replicas remain after that?
- Scale down your deployment by changing the replicas to 3 (you can modify the .yaml file directly, or use `kubectl edit` if you're familiar with vim). List all pods again. What do you observe?