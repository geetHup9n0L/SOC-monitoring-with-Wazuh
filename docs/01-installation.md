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
* Download and run the Wazuh installation assistant:

  First, we have to elevate to root user to implement the next steps:
  ```
  sudo bash
  ```
  ```bash
  curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
  ```
* Once the assistant finishes the installation, the output shows the access credentials and a message that confirms that the installation was successful.
  
  ```bash
  INFO: --- Summary ---
  INFO: You can access the web interface https://<WAZUH_DASHBOARD_IP_ADDRESS>
      User: admin
      Password: <ADMIN_PASSWORD>
  INFO: Installation finished.
  ```

### Wazuh Agents
```
- Clone another Ubuntu VM and Window VM as endpoints with Wazuh Agents
```


More documentation at: https://documentation.wazuh.com/current/index.html




