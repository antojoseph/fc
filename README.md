# Requirements - Minikube Cluster
-----------------
#afl-master (1) is a deployment - single instance 
#afl-slave ( n ) is a deployment that you can scale using kubectl scale --replicas=3 rs/foo 
#verify by kubectl exec -it k8s-master-pod-name-here /bin/bash 
#afl-whatsup /syncdir
