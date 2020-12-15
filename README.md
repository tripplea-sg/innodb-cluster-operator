# Triplea-Operator
Triplea-Operator is used to automate the deployment and life cycle of InnoDB Cluster using MySQL Enterprise Edition on Kubernetes or Openshift </br>
1. It’s a sidecar container that monitor the state of InnoDB Cluster
2. Automatic configuration of InnoDB Cluster on Containers
3. Automatic cluster membership management 
4. Adding or removing members 
5. Network partition or pod’s failure
6. Reboot cluster from complete outage 
7. Ad-hoc and scheduled backup using MySQL Enterprise Backup
8. Support online full backup, incremental backup and differential backup
</br> 
Triplea-operator is not really a Kubernetes Operator </br>
Simple architecture, easy to deploy, and with minimum dependency
![Image of picture3](https://github.com/tripplea-sg/innodb-cluster-operator/blob/main/Triplea-architecture.png)
