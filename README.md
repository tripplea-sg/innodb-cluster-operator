# Triplea-Operator
Triplea-Operator is used to automate the deployment and life cycle of InnoDB Cluster using MySQL on Kubernetes or Openshift or OKE </br>
1. Available on Public Docker Registry
2. Simple concept, easy to setup
3. Portable, able to run on Kubernetes / Openshift / OKE
4. It’s a sidecar container that monitor the state of InnoDB Cluster
5. Automatic configuration of InnoDB Cluster on Containers
6. Automatic cluster membership management 
7. Automatic adding or removing members 
8. Network partition or pod’s failure handling
9. Reboot cluster from complete outage handling
10. Ad-hoc and scheduled backup using MySQL Shell dumpInstance
</br> 
Triplea-operator is not really a Kubernetes Operator </br>
Simple architecture, easy to deploy, and with minimum dependency </br>

![Image of Yaktocat](https://github.com/tripplea-sg/innodb-cluster-operator/blob/main/Triplea-architecture.png)
