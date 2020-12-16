# Sample Commands
## A. On Kubernetes
### A.1. Namespace:
```
kubectl create ns mysql-cluster
```
### A.2. Service account:
```
kubectl apply -f k8s-service-account.yaml
```
### A.3. Roles:
```
kubectl apply -f k8s-role.yaml
```
### A.4. Role Bindings:
```
kubectl apply -f k8s-role-binding.yaml
```
### A.5. Deploy InnoDB Cluster with No-PV-PVC using Triplea-operator
```
kubectl apply -f k8s-mysql-no-disk.yaml
```
### OR, Deploy InnoDB Cluster with PV and PVC using Triplea-operator
```
kubectl apply -f k8s-mysql-with-disk.yaml
```
### A.6. Check innoDB Cluster
```
kubectl -n mysql-cluster exec -it mysql-0 -- mysqlsh root:root@localhost:3306 -- cluster status
```
### A.7. Backup mysql-0
```
kubectl apply -f k8s-mysql-backup.yaml
```
### A.8. Check Triplea-operator agent's log
```
kubectl -n mysql-cluster logs mysql-0 -c agent
```
## B. On Openshift
### B.1. Create Project / Namespace
```
oc create ns db-mysql-dev
```
### B.2. Service Account
Login as kubeadmin
```
oc apply -f oc-service-account.yaml
```
### B.3. Roles
Login as kubeadmin
```
oc apply -f oc-role.yaml
```
### B.4. Role Binding
Login as kubeadmin
```
oc apply -f oc-role-binding.yaml
```
### B.5. Deploy Template
Login as system:admin and set project as 'db-mysql-dev', then run the following:
```
oc apply -f oc-mysql-template.yaml
```
### B.6. Deploy InnoDB Cluster with PV and PVC using Template
```
oc process -n db-mysql-dev mysql-generic -p namespace=db-mysql-dev -p imageName=172.30.1.1:5000/db-mysql-dev/mysql-enterprise:latest -p statefulsetname=mysql -p replicas=3 -p secretpassword=mysql-root-password | oc create -f -
```
### B.7. Check Cluster
```
oc exec -it mysql-0 -- mysqlsh root:root@localhost:3306 -- cluster status
```
### B.8. Backup mysql-0
```
oc apply -f oc-mysql-backup.yaml
```
### B.9. Check Triplea-operator agent's log
```
oc logs mysql-0 -c agent
```
