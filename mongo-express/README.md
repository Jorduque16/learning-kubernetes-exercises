# MONGO - EXPRESS EXERCISE

The main idea for this project is setup and mongo express application to be accesible from the web browser allowing me to connect to my mongo db and execute many commands.

## References

Youtube video: [Kubernetes Tutorial for Beginners](https://www.youtube.com/watch?v=X48VuDVv0do)

## Annotations

- Deployment manages a Replicaset
- Replicaset manages a Pod
- Pod is an abstraction of a Container
- Container store the application

## COMPONENTS

- 2 Deployment / Pod
- 2 Service
- 1 ConfigMap
- 1 Secret
- 1 ingress

## COMMANDS EXECUTED:

``` bash

kubectl get nodes
kubectl get pods
kubectl get deployment
kubectl get replicaset

kubectl create deployment nginx-deployment --image=nginx
kubectl create deployment mongo-deployment --image=mongo

kubectl edit deployment nginx-deployment

kubectl delete deployment mongo-deployment

kubectl logs nginx-deployment-6d6565499c-lh7jq
kubectl describe pod mongo-deployment-555654868f-s5bnw

kubectl exec -it mongo-deployment-555654868f-s5bnw -- bin/bash

kubectl apply -f

kubectl get deployment nginx-deployment -o yaml > ./deployments/nginx-deployment-result.yaml

echo -n 'username' | base64
echo -n 'password' | base64

kubectl apply -f mongodb-secret.yml
kubectl apply -f mongo-deployment.yml

kubectl get pod --watch
kubectl get service

# Check if teh service is attached correctly
kubectl describe service mongodb-service

# Get extended pod information
kubectl get pod -o wide
kubectl get all | grep mongodb

kubectl apply -f dashboard-ingress.yaml

kubectl get pods -n ingress-nginx --watch



```

## TESTING

In order to test this, we should modify our /etc/host file to add the next line:

``` bash
vim /etc/hosts

{IP}  dashboard.com

```