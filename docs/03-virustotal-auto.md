# VirusTotal Integration:
### Overview:
- Enables VirusTotal intergration into Wazuh server, requires VirusTotal’s API Key
- Wazuh Config file at: `/var/ossec/etc/ossec.conf`, add the VTs API Key syntax to the config file
___
Prerequisite:
* Initially, we need to create an account on VirusTotal
  https://www.virustotal.com/gui/home/upload
* To acquire VirusTotal automation process integrated into Wazuh, we find its API Key:
  <img width="1350" height="819" alt="image" src="https://github.com/user-attachments/assets/cd6384c4-0ab7-4092-98ac-c68dad7d60cb" />
  <img width="1349" height="823" alt="image" src="https://github.com/user-attachments/assets/afbda54b-91bb-4b30-a2ea-476907947645" />
  
  <img width="1345" height="746" alt="image" src="https://github.com/user-attachments/assets/04fa0194-99e6-4ef1-a914-290c1641a97e" />
  For personal homelab, we are using default standard account which has limitation:
  * 4 lookups / min
  * 500 lookups / day
  



___
More related documentations at:
* Wazuh: https://documentation.wazuh.com/current/user-manual/capabilities/malware-detection/virus-total-integration.html
* VirusTotal: https://docs.virustotal.com/



