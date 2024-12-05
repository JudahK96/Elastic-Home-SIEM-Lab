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

<br/>
<br/>

## Adding Agent to KaliVM
| Agent Install| Confirming Install |
|-----------------------------------------------|----------------------------|
| ![Screenshot 2024-12-04 155838](https://github.com/user-attachments/assets/1ae13e05-2914-4592-a99b-53e527ef561f)|![Screenshot 2024-12-04 155900](https://github.com/user-attachments/assets/431efe44-10e1-42ba-9b69-1ae64ea8dcdc)|

Recieved a positive response when confirming installation with (sudo systemctl status elastic-agent.service).

<br/>
<br/>

## Generating security events through KaliVM
![Screenshot 2024-12-04 134839](https://github.com/user-attachments/assets/61f51b9e-f5eb-4ecc-9a1c-52077c771989)

| All Elastic Logs| Refinded Search for nmaps|
|-----------------------------------------------|----------------------------|
|![Screenshot 2024-12-04 164402](https://github.com/user-attachments/assets/d4e4d969-18d1-47d6-bb12-ebceecfc9bea)|![Screenshot 2024-12-04 164529](https://github.com/user-attachments/assets/d2bd3a30-cd4b-46e0-81ce-896099651bef)

Specified search to only show nmap events.

<br/>
<br/>

## Visualizing Events with a Dashboard
|Table 1|Table 2|Table 3|
|-----------------------------------------------|-----------------------------------------------|-----------------------------------------------|
|![Screenshot 2024-12-04 143412](https://github.com/user-attachments/assets/7dd84bfd-f7dc-4647-957b-32a78e94190a)|![Screenshot 2024-12-04 153144](https://github.com/user-attachments/assets/e11e61c8-86be-4f18-8421-d778749caad8)|![Screenshot 2024-12-04 165226](https://github.com/user-attachments/assets/02799d3d-f868-439a-80a4-48b527759340)

Using the "Count" and "Timestamp" fields, I created a easy to read tabel that shows the count of events ofver time. In the future I will add more set of agents to flesh out more advanced data tables.

<br/>
<br/>

## Detection Alerts w/Integrated Push Emails
![Screenshot 2024-12-04 165311](https://github.com/user-attachments/assets/24dc414a-cd7d-4ec7-aaef-f4a7ab679a6c)
Currently no alerts as triggers have not been specified. Although, there are some preset rules it is more convenient to flesh out from scratch.
### Basic set up for scanning
![Screenshot 2024-12-04 165643](https://github.com/user-attachments/assets/62cc810b-4846-4539-a0ca-c3d6b973fc04)
Creating new rules and defining those rules with a custom query. I set the conditions to detect nmap scan evenrts and also sudo elevated privilege events. I then set the action when triggered to send a push notification via email.
(Can also be intergrated with Jira, Slack meessages or custom webhooks)
 

| Sudo CMD Telemetry| Log Event for Sudo CMD| Push Email Notification|
|-----------------------------------------------|-----------------------------------------------|-----------------------------------------------|
|![Screenshot 2024-12-04 184054](https://github.com/user-attachments/assets/90f93a36-bd37-4d1b-922d-ef62343d1fca)|![Screenshot 2024-12-04 184235](https://github.com/user-attachments/assets/bb62f631-f190-4486-8543-8b3e1c5c22e7)|![Screenshot 2024-12-04 184038](https://github.com/user-attachments/assets/aa32c319-2295-428a-ac01-7bd9c7f62798)|

### Alert Events for nmaps and sudo cmds
![Screenshot 2024-12-04 184321](https://github.com/user-attachments/assets/583cf8a3-9681-4791-ac36-e035ad84ed85)
The sudo alert is now being triggered, pushing notifications every new instance within a set range of time.
