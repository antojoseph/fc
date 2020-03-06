## Requirements  <br />
Minikube Cluster  <br />
#afl-master (1) is a deployment - single instance  <br />
#afl-slave ( n ) is a deployment that you can scale using kubectl scale --replicas=3 rs/foo  <br />
#verify by kubectl exec -it k8s-master-pod-name-here /bin/bash  <br />
#afl-whatsup /syncdir <br />
