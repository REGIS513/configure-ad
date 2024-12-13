<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create a Resource Group
- Create a Virtual Network and Subnet
- Create the Domain Controller VM (Windows Server 2022) named DC-1
- Login to the VM using your username and password
- Create another VM named Client-1 using Windows 10
- Login to that VM using your user name and password
- Make sure to use the same Virtual Network and region as DC-1
- After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
- From the Azure Portal, restart Client-1
- Login to Client-1
- Attempt to ping DC-1’s private IP address
- From Client-1, open PowerShell and run ipconfig /all

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/lH7Mlq8.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install Active Directory, Login to DC-1 and install Active Directory Domain Services, Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is) Restart and then log back into DC-1 as user: mydomain.com\labuser


</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within Active Directory Users and Computers you can create an Organizational Unit and therefor add employees and admins to their selective Units. Adding a user to the Admins OU gives you access to join the domain controller from the Client-1 Virtual Machine.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into Client-1 as mydomain.com\(username here) -> Open system properties -> Click “Remote Desktop” -> Allow “domain users” access to remote desktop, you can now log into Client-1 as a normal, non-administrative user.

</p>
<br />
