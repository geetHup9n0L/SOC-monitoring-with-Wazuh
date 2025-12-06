## Environment Setup and Installation:
### I. Enviroment Setup
Our environment will be virtualized through the use of VMware

https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion

We will simulate the lab with different Virtual Machines acts as Server and Endpoints:

* 1 Ubuntu 24.04LTS: Wazuh Manager
* 1 Window 10 x64: Wazuh Agents
* 1 Ubuntu 24.04LTS (2): Wazuh Agents

Here are .iso files links:
* https://ubuntu.com/download/desktop
* https://www.microsoft.com/en-us/software-download/windows10

Here is diagram of our lab:
<img width="1075" height="553" alt="image" src="https://github.com/user-attachments/assets/516fa699-20e7-46a2-a862-bdb396efea59" />

### II. Installation:
Overview installation as mentioned:
* 1 Ubuntu 24.04LTS: Wazuh Manager
* 1 Window 10 x64: Wazuh Agents
* 1 Ubuntu 24.04LTS (2): Wazuh Agents

- Setting up Wazuh on this Ubuntu VM as Wazuh Manager (Website using local IP) :
  ```
  /ifconfig (inet)
  ```

- Clone another Ubuntu VM and Window VM as endpoints with Wazuh Agents
