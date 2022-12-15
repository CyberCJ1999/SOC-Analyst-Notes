Incident Handling - Scenario
Investigate a cyber attack in which the attacker defaced an organization's website. This organization has Splunk as a SIEM solution setup.

**Cyber Kill Chain**
Map the attacker's activity in each phase during the investigation
</BR>
- Reconnaissance
- Exploitation
- Installation
- Actions on Objectives
- Command and Control
- Weaponization Phase
- Delivery
* * *
**Scenario**
A Big corporate organization Wayne Enterprises has recently faced a cyber-attack where the attackers broke into their network, found their way to their web server, and have successfully defaced their website http://www.imreallynotbatman.com. 
Their website is now showing the trademark of the attackers with the message YOUR SITE HAS BEEN DEFACED.
* * *
**Splunk**
Logs used from 
- Webserver
- Firewall
- Suricata [IDS]
- Sysmon

Note: All the event logs that we are going to investigate are present in index=botsv1
* * *
**Interesting log sources**        </br>    
`wineventlog`    It contains Windows Event logs   </br>                                                                                                                                                                                    
`winRegistry`           It contains the logs related to registry creation / modification / deletion etc.                                                 </br>                                             
`XmlWinEventLog` It contains the sysmon event logs. It is a very important log source from an investigation point of view.                    </br>                                                         
`fortigate_utm` It contains Fortinet Firewall logs                                       </br>   

`iis` It contains IIS web server logs                                             </br>                                                                                                                                     
`Nessus:scan` It contains the results from the Nessus vulnerability scanner                                                                             </br>                                                
`Suricata` It contains the details of the alerts from the Suricata IDS.   This log source shows which alert was triggered and what caused the alert to get triggered— a very important log source for the Investigation </br>    
                                    
`stream:http` It contains the network flow related to http traffic   </br>  

`stream:DNS` It contains the network flow related to DNS traffic                                                                                              </br>                                                 
`stream:icmp` It contains the network flow related to icmp traffic        </br>                                                                             
