# Kuma Mesh - Policies
## Prerequisites for using these Kuma Policies
* Kubernetes cluster - Build K8s cluster using Minikube https://minikube.sigs.k8s.io/docs/start/
* Install Kuma Mesh - https://kuma.io/docs/1.3.0/installation/kubernetes/
## Getting Started
Explore below Kuma Mesh policies which can be applied for service to service communication within the mesh - 
* MTLS
* Traffic permission
* Traffic route
* Rate limiting
## Steps to implement the policies defined above 
1) Deploy demo app and redis from https://github.com/kumahq/kuma-counter-demo
2) Once the pods are running then apply mtls.yaml to encrypt the traffic between services.
```
kubectl apply -f kuma-mesh-policies/policies/mtls.yaml
```
3) Apply traffic-permission.yaml to allow traffic to the authorized destination service.
```
kubectl apply -f kuma-mesh-policies/policies/traffic-permission.yaml
```
4) Create different version of redis and apply traffic-route.yaml for blue/green or canary deployments for redis services.
```
kubectl apply -f kuma-mesh-policies/deployment/kuma-demo-redis.yaml -n kuma-demo
kubectl apply -f kuma-mesh-policies/policies/traffic-route.yaml
```
5) Apply rate limiting policy to limit the traffic for destination service.
```
kubectl apply -f kuma-mesh-policies/policies/rate-limit.yaml
```
## Contributers
Name | Email Id
--- | --- | 
Saravanan Periyasamy | saravanancse03@gmail.com
Anup Kumar Rai | raianup.2407@gmail.com
