# k8s-sandbox
A hands-on playground of Kubernetes YAMLs and examples for learning, testing, and experimenting with core K8s concepts.


PODS
```bash
kubectl apply -f podcreatemanifest.yaml
kubectl get pods
kubectl describe pod nginx
kubectl delete -f pod nginx
```
Namespaces
```bash
kubectl get namespaces
kubectl get pods -n kube-system
kubectl create ns demo
kubectl create -f resource-qouta-namespace.yaml --namespace=demo
```
Resources
```bash
kubectl top pods
brew install watch
watch -n 0.1 kubectl describe ns demo
kubectl apply -f simple-pod-with-resources.yaml
```
Kube exec and cp

ConfigMap
```bash
vim heros.txt
kubectl create cm demo-heros
kubectl create cm demo-heros --from-file heros.txt
kubectl describe cm demo-heros
kubectl apply -f pod-with-config-map.yaml
kubectl exec -it demo-pod -- sh  
ls
cd heros
ls
cat heros.txt
```
Deployment
```bash
kubectl apply -f deployment.yaml
watch -n 0.1 kubectl get pods -L app
```

Service
```bash
kubectl expose deploy  nginx-deployment
kubectl get services
kubectl describe svc nginx-deployment
```
