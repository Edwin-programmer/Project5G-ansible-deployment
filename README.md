# 5G network deployment - Ansible and Kubernetes
5G cloud-native integration and orchestration using the Open Network Automation Platform (ONAP) to deploy Cloud Native Functions (CNFs): OpenAirInterface (OAI) Cloud Radio Access Network (CloudRAN)

**Table of Contents**

- [Project Overview](#project-overview)
- [Documentation](#documentation)
  - [Docker](#docker)
    - [Installation](#installation)
    - [Configuration steps](#configuration-steps)
 - [Kubernetes](#kubernetes)
    - [Prerequisites](#prerequisites)
    - [Overview](#overview)
    - [Configuration](#configuration)
      - [IP tables](#ip-tables)
      - [Minikube](#minikube)
      - [Kubectl](#kubectl-native)
    - [Openvswitch, Multus and OVS-CNI Containers](#openvswitch,-multus-and-ovs-cni-containers)
    - [Kube-flannel & etcd-ha-operator](#kube-flannel-&-etcd-ha-operator)
    - [Deployments](#Deployments)
    - [Usage](#usage)
- [Group Information](#group-information)

## Project Overview

In this project we explore the fifth generation (5G) cloud native solution as Mobile Network Operators (MNOs) need to integrate and test multiple components from the orchestration to the infrastructure level, including the applications and terminals. This demonstrates possibilities for reducing Operational Expenditures and injecting automation in the MNOs’ mobile network infrastructure.

## Documentation

User documentation can be found below for the two options deployed for the project
- [Project setup using Docker](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Docker%20deployment/README.md)
- [Project setup using Kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment/README.md)
- Additional documentation can be found within the repository Wiki page  [Full documentation](https://github.com/Edwin-programmer/Project5G-ansible-deployment/wiki)
        
## Authors:
- **Kamal Isleem** _(GitHub: kamal2isleem)_
- **Samuel Hanson Hagan** _(GitHub: SamuelHagan-Carleton)_
- **Edwin Omoigui** _(GitHub: Edwin-programmer)_
- **Muhammad Shafayat Oshman** _(GitHub: Shafayat19)_

**Organization:** Carleton University - Advanced Topics in Communications Systems (SYSC5804 - 5G Networks)
