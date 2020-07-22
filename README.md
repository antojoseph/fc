![](https://raw.githubusercontent.com/antojoseph/fc/master/resources/logo.png)

[![place-holder](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](palce-holder)

Distributed fuzzing infrastructure with k8s, ceph for state sharing and elk stack for monitoring!

  - scale your fuzzing workloads
  - resilient sate sharing using ceph 
  - cluster performace monitoring with elastic,metric-beats and kibana


# To-Do 
  - Squash Container Image


# Planned Features!
  - Support afl++
  - Helm Charts to make deployment easier 
  - CI/CD system for continous fuzzing 
  



### Tech

FuzzCube uses a number of open source projects:

* [afl] - the mighty afl
* [libFuzzer] - powerful in-process fuzzing
* [k8s] - Container Orchestration!
* [ceph] - Distributed Object Storage
* [elastic] - Visibility for k8s.

And of course FuzzCube itself is open source with a public repository on GitHub.

### Test Cluster using minikube
FuzzCube requires a working k8s cluster to run.
Install minikube and deploy the yaml spec to start fuzzing.
```sh
#install minikube
$brew install minikube
#or to update your existing installation
$brew update
$brew upgrade minikube

#deploy a k8s cluster with 4 cpu , 8gigs of memory , 20 gigs of storage and log startup to console
$minikube -p clustername start --cpus=4 --memory=8192 --disk-size 20GB --alsologtostderr -v=7

# deploy dashboard for a neat UI to see everything in your cluster
$minikube dashboard -p clustername

#deploy metrics-server required by k8s to measure performance
$minikube addons -p clustername metrics-server

# to view resource utilization in the cluster
$kubectl top pod --all-namespaces | sort --reverse --key 3 --numeric 

#to check what cluster you are working with 
$kubectl config get-contexts

# get all pods in the cluster ( all -namespaces )
$kubectl get pods -A

# get a shell inside a pod inside the cluster (for debugging ) 
$kubectl exec -it podnamehere /bin/bash

```
### Installation

to deploy the fuzzer , have kubectl configured to use the cluster of choice . If you follow the above steps , this will be done for you!

```sh
$ git clone https://github.com/antojoseph/fc
$ cd fc
$ kubectl apply -f spellbook.yaml
$ kubectl apply -f afl.yml
$ kubectl apply -f libfuzzer.yml
$ kubectl apply -f debug.yml
```

For production environments...

```sh
$ change your ceph configuration to multi-node for resilience
```

### Debugging 

Use hyperkit driver for minikube if you are running OSX

```$ minikube start --driver=hyperkit --cpus=4 --memory=8192 --disk-size 20GB --alsologtostderr -v=7```


### Youtube Demo

[![Distributed Fuzzing with kubernetes and AFL](http://img.youtube.com/vi/FMOBS3a4Tnk/0.jpg)](https://youtu.be/DPsi7djs1d8 "Distributed Fuzzing with kubernetes")

### Credits

* [saadrana219] - for sharing  your wisdom 

License
----
Apache License 2.0

**Free Software, Hell Yeah!**


[afl]: <https://github.com/google/AFL>
[libfuzzer]: <https://llvm.org/docs/libFuzzer.html>
[k8s]: <https://github.com/kubernetes/kubernetes> 
[ceph]: <https://github.com/ceph/ceph>
[elastic]: <https://github.com/elastic>
[saadrana219]: <https://github.com/saadrana219>
