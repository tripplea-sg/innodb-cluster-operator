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
### Check innoDB Cluster
```
kubectl -n mysql-cluster exec -it mysql-0 -- mysqlsh root:root@localhost:3306 -- cluster status
```
### Backup mysql-0
```
kubectl apply -f k8s-mysql-backup.yaml
```
## Openshift
### Create Project / Namespace
```
oc create ns db-mysql-dev
```
### Service Account
Login as kubeadmin
```
oc apply -f oc-service-account.yaml
```
### Roles
Login as kubeadmin
```
oc apply -f oc-role.yaml
```
### Role Binding
Login as kubeadmin
```
oc apply -f oc-role-binding.yaml
```
### Deploy Template
Login as system:admin and set project as 'db-mysql-dev', then run the following:
```
oc apply -f oc-mysql-template.yaml
```
### Deploy InnoDB Cluster with PV and PVC using Template
```
oc process -n db-mysql-dev mysql-generic -p namespace=db-mysql-dev -p imageName=172.30.1.1:5000/db-mysql-dev/mysql-enterprise:latest -p statefulsetname=mysql -p replicas=3 -p secretpassword=mysql-root-password | oc create -f -
```
### Check Cluster
```
oc exec -it mysql-0 -- mysqlsh root:root@localhost:3306 -- cluster status
```
### Backup mysql-0
```
oc apply -f oc-mysql-backup.yaml
```
