**SIEM**
- Security Information and Event Management system
- tool that collects data from various endpoints/network devices across the network, stores them, and performs correlation on them
* * *
**Network Visibility through SIEM**
- understand why it is important to have better visibility of all the activities within a network

Example of a simple network:
- multiple Linux/Windows based endpoints
- 1 data server
- 1 web server
- devices communicate and access the internet through a router
- each network component can have one or more log sources generating different logs

* * *

Divide our network log sources into 2 logical parts:

1. Host-Centric Log Sources

These are log sources that capture events that occurred within or related to the host.
- log sources that generate host-centric logs are: Windows Event Logs, Sysmon, Qsquery

Host-Centric Logs are:
- user accessing a file
- user attempting to authenticate
- a process Execution Activity
- Powershell execution
- a process adding/editing/deleting a registry key or value
</br>

2. Network-Centric Log Sources

Logs are generated when hosts communicate with each other or access the internet to visit a website.
- network based protocols: SSH, VPN, HTTP/s, FTP

Events:
- SSH connection
- a file being accessed via FTP
- web traffic
- user accessing company resources through VPN

* * *

**Importance of SIEM**
- all devices on network generate hundreds of events per second > examining logs on each device can take a long time
- advantage of SIEM > ability to correlate between events, search through the logs, investigate incidents and respond promptly



**Key features of SIEM:**
- real time log ingestion
- alerting against abnormal activities
- 24/7 monitoring and visibility
- protection against the latest threats through early detection
- data insights and visualization

* * *

**Log Sources** 
- every device on the network generates some kind of log

Windows machine
- records every event > Event Viewer
- assigns a unique ID to each type of log activity
- Event Viewer > Windows Logs > Application/Security/Setup/System

Linux machine
- stores all related logs, events, errors, and warnings 
Common locations for Linux logs:
`/var/log/httpd` contains HTTP request / response and error logs
`/var/log/cron` events related to cron jobs are stored in this location
`/var/log/auth.log` and `/var/log/secure` store authentication related logs
`/var/log/kern` stores kernel related events

Web Server
- important to keep an eye on all the requests/responses coming in and out of the webserver 
In Linux, common locations to write all apache related logs:
`/var/log/apache` or `/var/log/httpd`
* * *
**Log Ingestion**
- all the above logs provide a wealth of information and can help identify security issues
- each SIEM solution has its own way of ingesting the logs

SIEM solutions:
1)	Agent/Forwarder
- SIEM solution provides a tool called an agent (forwarder by Splunk) that gets installed in the Endpoint
- it is configured to capture all the important logs and send to SIEM server

2)	Syslog
- widely used protocol to collect data from various systems like web servers + databases
- send real time data to the centralized destination

3)	Manual Upload
- some SIEM solutions (Splunk and ELK) allow users to ingest offline data for quick analysis
- once the data is ingested, it is normalised and made available for analysis

4)	Port Forwarding
- SIEM solutions can also be configured to listen on a certain point, and then endpoints forward the data to the SIEM instance on listening port


