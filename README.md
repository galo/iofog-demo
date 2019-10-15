# iofog-demo

Setting up a cluster with [iofog](https://iofog.org/). 

Iofog system runs as a Fog Controller and a set of IoFogAgents on each of the devices.

![iOFigArchitecture](docs/diagramiofog.jpg)

The ComnSat or Connector helps to stablish teh network between the controller and the nodes that run that agents.

The next steps will setup the IoFog running on a local device in Docker compose. It is also possible to run the [IoFog Controller on Kubernetes](https://edgeworx.io/kubernetes) by installer it using the [helm charts](https://github.com/eclipse-iofog/helm)


## Build iofogctl

You can use the packaged version, which did nto work in my case

```bash
curl https://packagecloud.io/install/repositories/iofog/iofogctl/script.deb.sh | sudo bash
sudo apt-get install iofogctl=1.3.0-beta
```

Instead you can also build iofogctl from the source code. since iofogctl still depends on 'dep', you will need to [install it](https://golang.github.io/dep/docs/installation.html)

The you can checkout iofogctl repo and build it.

```shell
git clone git@github.com:eclipse-iofog/iofogctl.git
cd iofogctl
make all
```

You can the check ioforctl is running the _iofogctl version_ command

```
iofogctl version
iofogctl Unified Cli

Copyright (C) 2019, Edgeworx, Inc.

version: 0.0.0-dev
platform: linux/amd64
commit: c74b764a7876127829489167d008eea3c4443a92
date: 2019-10-15T13:09:23-0600
```

## Install iofog Control Plane on Kubernetes

In this step we will setup ifogctl on kubernetes, you can use minikube, or microk8s. In this scenario I will use microk8s.

### Create Service Account for Tiller

Note that on RBAC enabled Kubernetes clusters (e.g. GKE, AKE) it is necessary to create a service account for Tiller before initializing helm. See helm init instructions for more details.

```
kubectl create -f build/eks/helm-service-account.yaml
helm init --service-account tiller
```

## Install OpenfaaS

The next step will be to setup OpenFaaS in [iofog]()


# References

1. [ioFog](https://iofog.org/docs/1.3.0/tutorial/get-to-know-iofog.html)