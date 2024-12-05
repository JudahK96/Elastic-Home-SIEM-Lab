# Elastic-Home-SIEM-Lab

## Objective
The scope of this project was to create a home lab for Elastic Stack Security Information and Event Management using the Elastic Web portal and a Kali Linux VM. Also, learning how to generate security events on the Kali VM, set up an agent to forward data to the SIEM, and query and analyze the logs in the SIEM.

### Skills Learned

- Configuring Elastic Agent on the Linux VM to collect the loogs and forward to the SIEM
- Generate security events on the Kali VM
- Query to find security events in the Elastic SIEm
- Create a visualization dashboard for security events
- Create aletrs for security events and forward alert via email

### Tools Used

- Virtualbox/ KaliLinux2024
- Elastic/ Kibana

## Adding Agent to KaliVM
| Agent Install| Confirming Install |
|-----------------------------------------------|----------------------------|
| ![Screenshot 2024-12-04 155838](https://github.com/user-attachments/assets/1ae13e05-2914-4592-a99b-53e527ef561f)|![Screenshot 2024-12-04 155900](https://github.com/user-attachments/assets/431efe44-10e1-42ba-9b69-1ae64ea8dcdc)|
Recieved a positive response when confirming instalation with (sudo systemctl status elastic-agent.service).
