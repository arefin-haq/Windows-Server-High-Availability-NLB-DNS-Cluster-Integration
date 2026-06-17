
     WINDOWS SERVER HIGH AVAILABILITY: NLB & DNS CLUSTER INTEGRATION


[ PROJECT OVERVIEW ]
A professional implementation of a Network Load Balancing (NLB) Cluster on 
Windows Server 2022. This project automates a scalable web infrastructure 
featuring a central Domain Controller and load-balanced IIS nodes.

[ SYSTEM ARCHITECTURE ]
* DC-SRV01 (AD DS/DNS)   : 192.168.2.201
* WEB-SRV01 (IIS/NLB)    : 192.168.2.202
* WEB-SRV02 (IIS/NLB)    : 192.168.2.203
* Cluster VIP (Endpoint) : 192.168.2.50

[ DEPLOYMENT WORKFLOW ]
1. Phase 1 (DC-SRV01) : Configure project.test forest & DNS [scripts/dc-setup.ps1]
2. Phase 2 (Web Nodes): Standardize IIS & NLB features [scripts/web01-setup.ps1]
3. Phase 3 (Cluster)  : Group nodes in Multicast mode with Port 80 affinity.

[ POST-DEPLOYMENT VERIFICATION ]
* Access via VIP : http://192.168.2.50
* Access via DNS : http://project.test

[ IMPLEMENTATION NOTES ]
* DNS Resolution : All nodes point to 192.168.2.201.
* Security       : Ensure Windows Firewall allows Port 80 & NLB traffic.
* Scalability    : Expand nodes using the 'Add-NlbClusterNode' cmdlet.

[ SECURITY NOTE ]
* This lab uses Port 80 (HTTP) for demonstration.
* For production, use Port 443 (HTTPS) with valid SSL/TLS certificates.

System Environment: Windows Server 2022
