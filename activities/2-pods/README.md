# Introduction to Kubernetes
Kubernetes is a popular container orchestration tool. Here is a guide to get you started with pods, the building blocks of any Kubernetes deployment.

## Demo
In the demo, we will be deploying a simple Hello World container to Kubernetes. Here are some of the common commands used in the demo:
- create Kubernetes resources from its manifest `kubectl apply -f <file name>`
- view all pods `kubectl get pods`
- describe a pod `kubectl describe pod <pod name>`
- view logs of pod `kubectl logs <pod name>`
- delete a pod `kubectl delete pod <pod name>`

## Challenge
Here is a sample pod manifest from the Kubernetes documentation. You would have to change some fields in order to make it work: 
```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```

Try to:
- Create a pod running your Express app
- Find out the IP address the pod is running on
- Try sending a curl request to the pod using the IP address that you obtained in the previous step. You can try using the command `kubectl run --image alpine/curl utils --restart=Never -- <curl command>`. This command spins up a pod in your cluster that performs the curl request.
- Try crashing your pod using by calling the `/crash` endpoint. Observe the subsequent behaviour and examine the pod status with `kubectl get pods`. Does the pod restart? What can you observe from the logs?
- Cleanup: delete the pod that you created