# File Integrity Monitoring Setup
Overview:
```
- Introduce to FIM (File Integrity Monitoring) enables the monitoring of an endpoint's filesystem to detect and alert on changes to specified files, directories, and Windows Registry keys.
- Congifure FIM on the Wazuh Agent (agent.conf), and inspect logs in FIM: Recent events
```
Initially, FIM (File Integrity Monitoring) already includes default, critical directories for both Windows (like C:\Windows\System32) and Linux

But its core function relies on explicitly defining the specific files and folders we want to monitor in your `ossec.conf`

On Ubuntu-enduser's machine, we will have FIM monitoring a defined directory additionally:
```
~/home/long/Downloads
```

And from Wazuh Server, and configure Agent centrally to run FIM on enduser's addition specific directory:

Starting at main dashboard, we find `Menu/Agents management/Group`:
<img width="1590" height="813" alt="image" src="https://github.com/user-attachments/assets/a6626044-ab96-403f-b8f9-a2b54621cdca" />


