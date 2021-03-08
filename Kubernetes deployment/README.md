 
# Using Kubernetes to deploy the 5G network

- [Prerequisites](#prerequisites)
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

Install `aaa_bbb` by running:

```shell
$ go get -u github.com/aaaaa_server
```

## Installation

Install `aaa_bbb` by running:

```shell
$ go get -u github.com/aaaaa_server
```

This will download and install the aaaaa binary into `$GOPATH/bin` directory.

## Configuration

See the [Tutorial](TUTORIAL.md) for more thorough setup instructions.

An example configuration file can be found in the 
