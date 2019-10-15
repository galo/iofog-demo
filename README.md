# iofog-demo

Setting up a cluster with [iofog](https://iofog.org/). 

Iofog system runs as a Fog Controller and a set of IoFogAgents on each of the devices.

![iOFigArchitecture](docs/diagramiofog.jpg)

The ComnSat or Connector helps to stablish teh network between the controller and the nodes that run that agents.

The next steps will setup teh IoFog running on a local device in Docker compose. It is also possible to run the [IoFog Controller on Kubernetes](https://edgeworx.io/kubernetes) by installer it using the [helm charts](https://github.com/eclipse-iofog/helm)


```bash
curl https://packagecloud.io/install/repositories/iofog/iofogctl/script.deb.sh | sudo bash
sudo apt-get install iofogctl=1.3.0-beta
```


## Install OpenfaaS

The next step will be to setup OpenFaaS in [iofog]()


# References

1. [ioFog](https://iofog.org/docs/1.3.0/tutorial/get-to-know-iofog.html)