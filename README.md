# Triplea-Operator
Triplea-Operator is used to automate the deployment and life cycle of InnoDB Cluster using MySQL on Kubernetes or Openshift or OKE </br>
1. It’s a sidecar container that monitor the state of InnoDB Cluster
2. Automatic configuration of InnoDB Cluster on Containers
3. Automatic cluster membership management 
4. Automatic adding or removing members 
5. Network partition or pod’s failure handling
6. Reboot cluster from complete outage handling
7. Ad-hoc and scheduled backup using MySQL Shell dumpInstance
</br> 
Triplea-operator is not really a Kubernetes Operator </br>
Simple architecture, easy to deploy, and with minimum dependency </br>

![Image of Yaktocat](https://github.com/tripplea-sg/innodb-cluster-operator/blob/main/Triplea-architecture.png)
