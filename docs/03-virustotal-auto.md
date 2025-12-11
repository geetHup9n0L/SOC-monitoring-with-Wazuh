# VirusTotal Integration:
### Overview:
- Enables VirusTotal intergration into Wazuh server, requires VirusTotal’s API Key
- Wazuh Config file at: `/var/ossec/etc/ossec.conf`, add the VTs API Key syntax to the config file
___
Prerequisite:
* Initially, we need to create an account on VirusTotal:
  
  https://www.virustotal.com/gui/home/upload
  
* To acquire VirusTotal automation process connected to Wazuh, we find its API Key:

  <img width="1349" height="823" alt="image" src="https://github.com/user-attachments/assets/afbda54b-91bb-4b30-a2ea-476907947645" />
  
  <img width="1345" height="746" alt="image" src="https://github.com/user-attachments/assets/04fa0194-99e6-4ef1-a914-290c1641a97e" />
  
  For personal homelab, we are using default standard account which has limitation:
  
  * `4 lookups / min`
  * `500 lookups / day`
  
Now, we need to enable the VirusTotal integration into our Wazuh server:
* First, add the integration module to Wazuh server's main configuration file, at:
  ```bash
  /var/ossec/etc/ossec.conf
  ```
  ```xml
  <integration>
    <name>virustotal</name>
    <api_key>API_KEY</api_key> <!-- Replace with your VirusTotal API key -->
    <group>syscheck</group>
    <alert_format>json</alert_format>
  </integration>
  ```
  At `API_KEY` placeholder, replace it with our prior API KEY from VirusTotal

  Example:
  
  <img width="806" height="69" alt="image" src="https://github.com/user-attachments/assets/93846dc4-2347-492f-b4f7-9269374c70d4" />
  
  * Inside the `ossec.conf` file, move to the bottom within the last `</ossec_config>...</ossec_config>` tag
  * Add the config module above:
    
  <img width="904" height="573" alt="image" src="https://github.com/user-attachments/assets/c5f4f1ec-046f-4a2c-a9fe-2144124d3f50" />



___
More related documentations at:
* Wazuh: https://documentation.wazuh.com/current/user-manual/capabilities/malware-detection/virus-total-integration.html
* VirusTotal: https://docs.virustotal.com/






