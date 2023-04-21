# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create resources within Azure.(Virtual Machines) 
- Ensure connectivity between DC-1 and Client-1
- Install Active Directory
- Create Admin and User accounts in AD.
- Join Client-1 to Domain
- Setup Remote Desktop for non-administrative users on Client-1

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/K9rxAn2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Creating resources(DC-1 AND Client-1) in Azure will be the first step.Set Domain Controller’s NIC Private IP address to be static. Ensure that both VMs are in the same Vnet.
</p>
<br />

<p>
<img src="https://i.imgur.com/vopB58k.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to Client-1 with Remote Desktop and ping DC-1’s private IP address with ping -t <ip address> (perpetual ping)
Login to the Domain Controller and enable ICMPv4 in on the local windows Firewall
Check back at Client-1 to see the ping succeed

</p>
<br />

<p>
<img src="https://i.imgur.com/9ZyJU8X.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to DC-1 and install Active Directory Domain Services
Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
Restart and then log back into DC-1 as user: mydomain.com\labuser

</p>
<br />
<p>
<img src="https://i.imgur.com/rLO2goo.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”
Create a new OU named “_ADMINS”
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin”
Add jane_admin to the “Domain Admins” Security Group
Log out/close the Remote Desktop connection to DC-1 and log back in as “mydomain.com\jane_admin”
User jane_admin as your admin account from now on

</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
