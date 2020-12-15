# Samples
## On Kubernetes
### Namespace:
```
kubectl create ns mysql-cluster
```
### Service account:
```
kubectl apply -f k8s-service-account.yaml
```
### Roles:
```
kubectl apply -f k8s-role.yaml
```
### Role Bindings:
```
kubectl apply -f k8s-role-binding.yaml
```
### Deploy InnoDB Cluster with No-PV-PVC using Triplea-operator
```
kubectl apply -f k8s-mysql-no-disk.yaml
```
### OR, Deploy InnoDB Cluster with PV and PVC using Triplea-operator
```
kubectl apply -f k8s-mysql-with-disk.yaml
```
