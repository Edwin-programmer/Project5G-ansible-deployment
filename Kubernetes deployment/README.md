 
# Using Kubernetes to deploy the 5G network

- [Prerequisites](#prerequisites)
- [Overview](#overview)
- [Installation](#installation)
- [Configuration](#configuration)
  - [IP tables](#ip-tables)
  - [Minikube](#minikube)
  - [Openvswitch, Multus and OVS-CNI Containers](#openvswitch,-multus-and-ovs-cni-containers)
  - [Kube-flannel & etcd-ha-operator](#kube-flannel-&-etcd-ha-operator)
  - [Checks](#checks)
    - [Repository Groups](#repository-groups)
    - [Repository Authentication](#repository-authentication)
    - [Organization Check](#organization-check)
- [Deployments](#Deployments)
- [Usage](#usage)


## Prerequisites

ubuntu-bionic-18.04 running - Kernel 5.0.0-23 generic
4G RAM, 10GHDD

```shell
$ go get -u github.com/aaaaa_server
```

## Overview

![Setup overview](https://github.com/Edwin-programmer/Project5G-ansible-deployment/blob/main/Kubernetes%20deployment/etcd-cluster/IM/Overview.jpg)





## Installation

Install `aaa_bbb` by running:

```shell
$ go get -u github.com/aaaaa_server
```

This will download and install the aaaaa binary into `$GOPATH/bin` directory.

## Configuration

# IP tables

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

See the [Tutorial](TUTORIAL.md) for more thorough setup instructions.

An example configuration file can be found in the 
