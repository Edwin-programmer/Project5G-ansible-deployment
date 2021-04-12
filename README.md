# 5G Network deployment - Ansible (with Docker) and Kubernetes
5G cloud-native orchestration using containers and automation to deploy Cloud Native Functions: OpenAirInterface (OAI), Cloud Radio Access Network (CloudRAN) and 5G Core Network Functions

**Table of Contents**

- [Project Overview](#project-overview)
- [Documentation](#documentation)
    * [Docker](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Docker%20deployment)
      + [Requirements](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Docker%20deployment#requirements)
      + [Configuration steps](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Docker%20deployment#configuration-steps)
  - [Kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment)
    - [Prerequisites](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#prerequisites)
    - [Overview](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#overview)
    - [Configuration](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#configuration)
      - [IP tables](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#ip-tables)
      - [Minikube](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#minikube)
      - [Kubectl](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#kubectl)
    - [Openvswitch, Multus and OVS-CNI Containers](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#kubectl)
    - [Kube-flannel & etcd-ha-operator](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#kubectl)
    - [Deployments](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment#Deployments)
- [Group Information](#authors)

## Project Overview

In this project we demonstrate the fifth generation (5G) cloud native solution deployments as Mobile Network Operators (MNOs) need to integrate and test multiple components from the orchestration to the infrastructure level, including the applications and terminals. This demonstrates possibilities for reducing Operational Expenditures and injecting automation in the MNOs’ mobile network infrastructure.

## Documentation

User documentation can be found below for the two options deployed for the project
- [Project setup using Docker](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Docker%20deployment/README.md)
- [Project setup using Kubernetes](https://github.com/Edwin-programmer/Project5G-ansible-deployment/tree/main/Kubernetes%20deployment/README.md)
- Additional documentation can be found within the repository Wiki page  [Full documentation](https://github.com/Edwin-programmer/Project5G-ansible-deployment/wiki)
        
##### Authors:
 
 -  <sup>**Kamal Isleem** _(GitHub: kamal2isleem)_
 -  **Samuel Hanson Hagan** _(GitHub: SamuelHagan-Carleton)_
 -  **Edwin Omoigui** _(GitHub: Edwin-programmer)_
 -  **Muhammad Shafayat Oshman** _(GitHub: Shafayat19)_</sup>

**Organization:** Carleton University - Advanced Topics in Communications Systems (SYSC5804 - 5G Networks)
