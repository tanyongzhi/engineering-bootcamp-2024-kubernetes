# Services
Previously, we were hitting the IP addresses of the pods directly. This does not allow for good service discovery. Because pods are ephemeral, the IP addresses associated with each pod can change at any time.

Services allow your pods to be exposed to other machines (both internal and external to the cluster).

## Demo
Here are some common commands to get your started:
- list all services: `kubectl get svc`

## Challenge
Here is a sample service manifest from the Kubernetes documentation. You would have to change some fields in order to make it work: 
```
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app.kubernetes.io/name: MyApp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
```

- Create a service to front the pods that you created in the previous chapter (when you created the deployments).
- Try sending a curl request to the service, hitting the `/hostname` endpoint.
> [!NOTE]
> You can reach a service using the following URL `<service name>.<namespace>.svc.cluster.local`
- What do you notice about the hostname returned for each invocation? 
- Observe the endpoints associated with the service using `kubectl describe <service name>`
- Try re-creating (deleting and re-applying) the deployment. Observe the endpoints associated with the service again (with `kubectl describe <service name>`). What do you notice about these values as compared to before re-creating the deployment? 
