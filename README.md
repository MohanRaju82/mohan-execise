# Steps to setup
- Start minikube cluster
- clone this repository to a folder
- run the following commads :
```
cd mohan-exercise
kubectl apply -f .
port=$(kubectl get svc nginx-svc -ojson | jq '.spec.ports[].nodePort')
ip=$(minikube ip)
hostname=$(echo $ip:$port)
curl -s $hostname
```