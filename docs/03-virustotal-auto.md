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
  * Add the config module above to that section and save the config file:
    
  <img width="904" height="573" alt="image" src="https://github.com/user-attachments/assets/c5f4f1ec-046f-4a2c-a9fe-2144124d3f50" />

  * And restart the Wazuh-Manager to update the configuration file
  ```
  systemctl restart wazuh-manager
  ```
  <img width="762" height="53" alt="image" src="https://github.com/user-attachments/assets/cbeb00aa-56da-4cd2-b883-2f80a241b421" />

* To test out the VirusTotal Integration, we will download a `EICAR test file` on Ubuntu-enduser's machine:
  ```
  An EICAR file is a safe, standard text file created by the European Institute for Computer Antivirus Research (EICAR) to test antivirus software without using real malware, triggering a detection alert due to a specific    character string, proving your security software is active and working correctly
  ```
  On Ubuntu-enuser's machine:
  
  <img width="815" height="117" alt="image" src="https://github.com/user-attachments/assets/a085c1bc-85e6-47c5-854e-aab481cee30b" />
  <img width="814" height="163" alt="image" src="https://github.com/user-attachments/assets/97f11f6e-412e-4e3e-ac9f-127059565e52" />

  Back to our Wazuh server, we confirm the event if it's triggered by alert


___
More related documentations at:
* Wazuh: https://documentation.wazuh.com/current/user-manual/capabilities/malware-detection/virus-total-integration.html
* VirusTotal: https://docs.virustotal.com/







