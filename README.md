Building a Virtual Lab with Active Directory - oscorp.local 
________________________________________
Overview
This customized guide walks you through building a complete Windows Server 2022 Active Directory environment using Oracle VirtualBox. You will simulate an enterprise network infrastructure in an isolated lab environment using a domain named oscorp.local.
By the end of this lab, you will have:
•	A Windows Server 2022 Domain Controller (OsCorp-ADC)
•	A Windows 11 Enterprise Client (OC-AdminPC) joined to the domain oscorp.local
•	Configured DHCP for automatic IP assignment (192.168.2.0/24)
•	Configured Group Policy to apply a desktop wallpaper
________________________________________
Lab Objectives
•	VirtualBox setup with internal networking
•	Windows Server 2022 installation and promotion to Domain Controller
•	Active Directory and DNS configuration
•	DHCP server setup with exclusions
•	Windows 11 client domain join
•	Group Policy Object (GPO) deployment for user experience
________________________________________
Network Plan
•	Network: 192.168.2.0/24
•	Static IP Range: 192.168.2.1 – 192.168.2.100
o	Domain Controller (OsCorp-ADC): 192.168.2.10
•	DHCP Range: 192.168.2.101 – 192.168.2.200
•	DNS: 192.168.2.10
________________________________________
Virtual Machines
•	OsCorp-ADC: Windows Server 2022
•	OC-AdminPC: Windows 11 Enterprise
________________________________________
Steps Summary
1.	Create Virtual Machines in VirtualBox
o	Set Adapter 1: NAT
o	Set Adapter 2: Internal Network (Name it: oscorp-net)

2.	Install Windows Server 2022 on OsCorp-ADC
o	Assign static IP: 192.168.2.10
o	Rename the server: OsCorp-ADC

3.	Install AD DS & Promote Server to Domain Controller
o	Domain: oscorp.local
o	Reboot and verify AD installation

4.	Install and Configure DHCP
o	Scope: 192.168.2.101 – 192.168.2.200
o	Exclude: 192.168.2.1 – 192.168.2.100

5.	Create Shared Folder for Wallpaper
o	Share wallpaper and set permissions to "Everyone: Read"

6.	Create GPO to Set Desktop Wallpaper
o	Link GPO to domain
o	Use gpupdate /force on OC-AdminPC

7.	Configure Windows 11 Client (OC-AdminPC)
o	Set DNS to 192.168.2.10
o	Join domain: oscorp.local
o	Reboot and log in with domain credentials
________________________________________
Testing & Verification
•	Use ping oscorp.local and nslookup for name resolution
•	Use ipconfig /all to verify DHCP assignment
•	Confirm wallpaper policy is applied via GPO
________________________________________
Learning Outcomes
•	Understanding of on-premises identity management
•	DHCP and DNS configuration for enterprise environments
•	AD domain join troubleshooting
•	GPO fundamentals and testing
________________________________________
Future Enhancements
•	Add second DC for redundancy
•	Enable NAT routing for internet on client
•	Deploy more GPO policies for security and compliance
•	Add user account management and OUs
________________________________________
Disclaimer
This lab is for educational purposes only. Hardening and security controls are required before any production use.
________________________________________
References
•	Microsoft Learn: https://learn.microsoft.com
•	Group Policy Settings: https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/gpupdate
•	DHCP Configuration: https://learn.microsoft.com/en-us/windows-server/networking/technologies/dhcp/dhcp-deploy-wps
•	ChatGPT for guidance - https://chatgpt.com/ 

