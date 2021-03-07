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
   
     
    
        
