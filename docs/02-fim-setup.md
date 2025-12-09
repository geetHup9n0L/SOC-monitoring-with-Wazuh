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
There are two methods of configuring FIM for Agents. They can either be configured locally with the Wazuh agent configuration file or remotely using the centralized configuration.

From Wazuh Server, we will configure Agent centrally to run FIM on enduser's addition specific directory:

Starting at main dashboard, we find `Menu/Agents management/Group`:
<img width="1590" height="813" alt="image" src="https://github.com/user-attachments/assets/a6626044-ab96-403f-b8f9-a2b54621cdca" />
```
Groups are powerful management tools for organizing agents, allowing central configuration and tailored monitoring for different sets of devices through group-specific agent.conf files
```

Inside the page, we can see our `default group` containing both of Agents

<img width="1591" height="585" alt="image" src="https://github.com/user-attachments/assets/809cd31c-c972-4797-8608-6deb4e174c48" />

With Group, it would be ideal if for example, in the future we want to add more Agents, and we want the same configuration to be applied to those Agents accordingly. 

The advantage would be that we wont have to manually configure its local .config file, which takes lot of time

To access the agent.conf file, find the pencil icon at "Action" column:
<img width="1590" height="603" alt="image" src="https://github.com/user-attachments/assets/03f8885e-677f-47a4-8767-680eee3bb3e6" />
<img width="1590" height="811" alt="image" src="https://github.com/user-attachments/assets/5aed7e2e-c9c2-4dfa-ba68-e14100d64512" />
