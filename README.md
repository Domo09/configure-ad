<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com/watch?v=lzHRxxSmQXc)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create the Domain Controller VM in Azure and name it DC-1 the Login with Remote Desktop
- Set DC-1 NIC private IP address to static and enable ICMPv4 on local firewall
- Create the Client VM named Client-1 (Use same resource group and vnet from DC-1)
- Login to CLient-1 with Remote Desktop and ping DC-1 private IP address with Perpetual Ping
- In DC-1 install Active Directory services and set upnew forest as (mydomain.com\labuser) then login under labuser
- In Active Directory Users and Computers (ADUC) create two Organizational Units (OU) labeled "_EMPLOYEES" and "_ADMINS"
- Creat random employee (Jane Doe) with username Jane_Admin then Add Jane to security groups
- Login to DC-1 as Jane_Admin
- In Azure portal, Set Client-1 DNS settingd to DC-1's private IP address and restart CLient-1
- Lohin to Client-1 as labuser and add to Domain Controller
- Verify that CLient-1 shows up in DC-1's ADUC inside "computers" container on root of Domian
- In Client-1, Open system properties, Click remote desktop and allow "domain Users" access to Remote Desktop
- In DC-1 (as Jane_Admin) Open Powershell_ise as an administrator
- Create a new file and paste contents of the "script" into it then run the script and observe the accounts being created
- Attempt to login into Client-1 with one of the Accounts


