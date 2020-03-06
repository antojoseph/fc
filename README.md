# Requirements
1. Minikube Cluster

afl-master (1) is a deployment - single instance \n
afl-slave ( n ) is a deployment that you can scale using kubectl scale --replicas=3 rs/foo    \n
verify by kubectl exec -it k8s-master-pod-name-here /bin/bash \n
afl-whatsup /syncdir
