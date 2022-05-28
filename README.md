# mac-k8s-bluegreen-sample 

### Deploy V1
```
kubectl apply -f deploy-v1.yml
```

### Deploy Service
```
kubectl apply -f service.yml
```

### Deploy V2
```
kubectl apply -f deploy-v2.yml
```

### Swich V1 to V2
Update `spec.selector.app` in service.yml then run below command
```
kubectl apply -f service.yml
kubectl delete deployment mac-app-v1-deployment
```

### Clean up
```
kubectl delete deployment mac-app-v1-deployment
kubectl delete deployment mac-app-v2-deployment
kubectl delete service mac-service
```