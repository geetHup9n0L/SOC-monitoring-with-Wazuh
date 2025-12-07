# Environment Setup and Installation:
## I. Enviroment Setup
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

## II. Installation:
Overview installation as mentioned:
* 1 Ubuntu 24.04LTS: Wazuh Manager
* 1 Window 10 x64: Wazuh Agents
* 1 Ubuntu 24.04LTS (2): Wazuh Agents

### Wazuh Manager
```
- Setting up Wazuh on this Ubuntu VM as Wazuh Manager (Website using local IP) :
  /ifconfig (inet)
```
We setup Ubuntu VM as a server to run the central components of Wazuh.

This Wazuh server will run all the core components, and its where SIEM, Web application take place, as well as where all Agents send its reports to.

Regarding hardware requirement for the server:

<img width="452" height="238" alt="image" src="https://github.com/user-attachments/assets/3d708901-5eb8-4a05-baef-95571cdafac0" />

* Our project scales within an individual homelab, so the first option greatly suffices our needs.

* And the server's version: Ubuntu 24.04LTS validate the supported architecture

Installing Wazuh on Server:

* First, we have to elevate to root user to implement the next steps:
  ```
  sudo bash
  ```
* Download and run the Wazuh installation assistant:
  ```bash
  curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
  ```
  <img width="918" height="94" alt="image" src="https://github.com/user-attachments/assets/d764a7cf-4152-4d97-98a2-ce79f846dafc" />

* Once the assistant finishes the installation, the output shows the access credentials and a message that confirms that the installation was successful.
  
  ```bash
  INFO: --- Summary ---
  INFO: You can access the web interface https://<WAZUH_DASHBOARD_IP_ADDRESS>
      User: admin
      Password: <ADMIN_PASSWORD>
  INFO: Installation finished.
  ```
  <img width="919" height="157" alt="image" src="https://github.com/user-attachments/assets/e1aec20b-b599-45ba-a2aa-fb1b3ea5b147" />

  Once the installation is finished, we can access the Wazuh Dashboard

  We are provided with credential, and the web interface at `https://<wazuh-dashboard-ip>:443`
   
    * We find `<wazuh-dashboard-ip>` with command `ip a`:
      
  <img width="1008" height="310" alt="image" src="https://github.com/user-attachments/assets/9112b0e4-a716-4572-8c8b-bea1c1808c1a" />

  On the web interface, login with provided credentials from before:
  
  <img width="648" height="722" alt="image" src="https://github.com/user-attachments/assets/f15fa03b-9e84-455c-a912-bee1f9b49950" />

  And here is our homepage of Wazuh:

  <img width="1852" height="897" alt="image" src="https://github.com/user-attachments/assets/635df29f-5700-44a2-b011-459f5fa2c792" />


### Wazuh Agents
```
- Clone another Ubuntu VM and Window VM as endpoints with Wazuh Agents
```
Now, to have Wazuh agents installed on endusers - our other VMs

On top-left of homepage, we deploy new Agents:

<img width="1853" height="897" alt="image" src="https://github.com/user-attachments/assets/205b8985-4ab0-43ef-8f6a-e7767ee19304" />



More documentation at: https://documentation.wazuh.com/current/index.html









