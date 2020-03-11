![](https://raw.githubusercontent.com/antojoseph/fc/master/resources/logo.png)

[![place-holder](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](palce-holder)

Distributed fuzzing with k8s and afl using ceph for state sharing , elk stack for monitoring!

  - scale your fuzzing workloads
  - resilient sate sharing using ceph 
  - cluster performace monitoring with elastic,metric-beats and kibana

# Planned Features!

  - Support afl++
  - Helm Charts to make deployment easier 



### Tech

FuzzCube uses a number of open source projects to work properly:

* [ k8s ] - Container Orchestration!
* [ceph] - Distributed Object Storage
* [elastic] - Visibility for k8s.

And of course FuzzCube itself is open source with a public repository on GitHub.

### Installation

FuzzCube requires a working k8s cluster to run.

Install minikube and deploy the yaml spec to start fuzzing.

```sh
$ git clone https://github.com/antojoseph/fc
$ cd fc
$ kubectl apply -f spellbook.yaml
```

For production environments...

```sh
$ change your ceph configuration to multi-node for resilience
```


License
----

MIT


**Free Software, Hell Yeah!**
