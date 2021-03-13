 
# Using Kubernetes to deploy the 5G network

- [Prerequisites](#prerequisites)
- [Overview](#overview)
- [Configuration](#configuration)
  - [IP tables](#ip-tables)
  - [Minikube](#minikube)
  - [Kubectl](#kubectl-native)
  - [Openvswitch, Multus and OVS-CNI Containers](#openvswitch,-multus-and-ovs-cni-containers)
  - [Kube-flannel & etcd-ha-operator](#kube-flannel-&-etcd-ha-operator)
  - [Checks](#checks)
    - [Repository Groups](#repository-groups)
    - [Repository Authentication](#repository-authentication)
    - [Organization Check](#organization-check)
- [Deployments](#Deployments)
- [Usage](#usage)


## Prerequisites

Host OS Configuration and Kernel setup should be as follows: Ubuntu-bionic-18.04 running with Kernel 5.0.0-23 generic
4G RAM, 10GHDD.
Ensure Docker is running, further steps for installation are at https://docs.docker.com/get-docker/
- Images from free5gc open-source were used. More details on free5gc can be found here https://www.free5gc.org/

```shell
$ sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu​ $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install -y docker-ce
```

## Overview

![Setup overview](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/overview_.jpg)

## Configuration

### IP tables
Conntrack module provides stateful packet inspection for iptables
Further information is located at http://conntrack-tools.netfilter.org/
```
sudo apt-get update -y
sudo apt-get install -y conntrack
```
Enable IP tables
```
echo "net.bridge.bridge-nf-call-iptables=1" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
```

### Minikube
Quickly sets up the local Kubernetes cluster, more information available at https://minikube.sigs.k8s.io/docs/start/
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
sudo -E minikube start --driver=none
sudo minikube start
```
### Kubectl
Configure kubectl using native package management. More details on setup are at https://kubernetes.io/docs/tasks/tools/
```
sudo apt-get update && sudo apt-get install -y apt-transport-https gnupg2 curl
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
```

### Kube-flannel & etcd-ha-operator
```
sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
sudo kubectl create -f https://raw.githubusercontent.com/openshift/etcd-ha-operator/master/deploy/rbac.yaml
sudo kubectl create -f https://raw.githubusercontent.com/openshift/etcd-ha-operator/master/deploy/crd.yaml
sudo kubectl create -f https://raw.githubusercontent.com/openshift/etcd-ha-operator/master/deploy/restore_crd.yaml
sudo kubectl create -f https://raw.githubusercontent.com/openshift/etcd-ha-operator/master/deploy/backup_crd.yaml
sudo kubectl create -f https://raw.githubusercontent.com/openshift/etcd-ha-operator/master/deploy/operator.yaml
sudo kubectl create -f https://raw.githubusercontent.com/openshift/etcd-ha-operator/master/deploy/cr.yaml
sudo kubectl get pods
```
![kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/pods_kubcluster.jpg)

### Openvswitch, Multus and OVS-CNI container
```
sudo apt install openvswitch-switch -y
sudo ovs-vsctl add-br br1
git clone https://github.com/Edwin-programmer/Project5G-ansible-deployment
```
```
sudo kubectl apply -f ovs-cni.yml
sudo kubectl apply -f https://raw.githubusercontent.com/intel/multus-cni/master/images/multus-daemonset.yml
sudo kubectl apply -f ovs-net-crd.yaml
sudo kubectl apply -f prom-node-exporter.yaml
nano ovs-net-crd.yaml

cat <<EOF >./ovs-net-crd.yaml
apiVersion: "k8s.cni.cncf.io/v1"
kind: NetworkAttachmentDefinition
metadata:
  name: ovs-net
  annotations:
    k8s.v1.cni.cncf.io/resourceName: ovs-cni.network.kubevirt.io/br1
spec:
  config: '{
      "cniVersion": "0.3.1",
      "type": "ovs",
      "bridge": "br1"
    }'
EOF
```

## Deployments
```
sudo kubectl apply -f nfvo-service-account-agent.yaml
sudo kubectl apply -f mysql-deploy.yaml
sudo kubectl apply -f kube5gnfvo.yaml
sudo kubectl apply -f 5gmano-deploy.yaml
```
```
sudo kubectl apply -f unix-daemonset.yaml
sudo kubectl apply -f free5gc-mongodb.yaml
sudo kubectl apply -f free5gc-configmap.yaml
sudo kubectl apply -f free5gc-nrf.yaml
sudo kubectl apply -f free5gc-ausf.yaml
sudo kubectl apply -f free5gc-smf.yaml
sudo kubectl apply -f free5gc-nssf.yaml
sudo kubectl apply -f free5gc-pcf.yaml
sudo kubectl apply -f free5gc-udm.yaml
sudo kubectl apply -f free5gc-udr.yaml
```
![kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/node.jpg)

## Web console 
(Require nodejs and yarn packages)
```
sudo apt remove cmdtest
	sudo apt remove yarn
	curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
	echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
	sudo apt-get update
	sudo apt-get install -y nodejs yarn
 ```
 ![kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/free5gc.jpg)
 ![kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/Listen.jpg)
 ![kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/Added%20sub.jpg)

See the [Tutorial](TUTORIAL.md) for more thorough setup instructions.

 
