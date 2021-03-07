# 5G-ansible-deployment-project
5G cloud-native integration and orchestration using the Open Network Automation Platform (ONAP) to deploy Cloud Native Functions (CNFs): OpenAirInterface (OAI) Cloud Radio Access Network (CloudRAN)

* [Project Overview](#project-overview)
* [Documentation](#documentation)
* [Group Information](#group-information)
* [Docker-5G-Deployment](#Docker-5G-Deployment)
## Project Overview

In this project we explore the fifth generation (5G) cloud native solution as Mobile Network Operators (MNOs) need to integrate and test multiple components from the orchestration to the infrastructure level, including the applications and terminals. This demonstrates possibilities for reducing Operational Expenditures and injecting automation in the MNOs’ mobile network infrastructure.

## Documentation

User documentation can be found in the Github repository at [Project5G ansible deployment documentation](https://github.com/Edwin-programmer/Project5G-ansible-deployment/wiki)

## Docker-5G-Deployment
### installation
The installation can be done directly over the host operating system (OS) or inside a virtual machine (VM).   

**System requirements**
- CPU type: x86-64 (specific model and number of cores only affect performance)
- RAM: 4 GB
- Disk space: 40 GB
- Ubuntu 18.04 LTS


**Steps**  
**1. Install python 2.7:**      
    
``` sudo apt update && apt -y install python ```    
     
        
**2. Install git :**    
  
  ``` sudo apt -y install git ```     
     
**3. Clone this repository:**   
  
    
  ``` git clone add link for the docker ``` 
    

**4. Clone this repository:**   
  
``` sudo apt -y install ansible ```   
  
    
**5. to go docker-file** 
  
``` cd folder name ```     
  
**6. Run ansible-play book to deploy 5G network**  
   
``` ansible-playbook -K our-doker.yml  -e  "internet_network_interface=<< internet network interface name>>" ```    
   
     
    
        
        
## Group Information

**Organization:** Carleton University (SYSC5804 - 5G Networks)

### Authors:

**1. Kamal Isleem**
 - GitHub: kamal2isleem

**2. Samuel Hanson Hagan**

 - GitHub: SamuelHagan-Carleton

**3. Edwin Omoigui**

 - GitHub: Edwin-programmer

**3. Muhammad Shafayat Oshman**

 - GitHub: 
