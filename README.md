On-Premises Active Directory Deployed in the Cloud (Azure)
<p align="center"> <img src="https://i.imgur.com/DJmEXEB.png" width="80%" alt="AD Deployment Banner"/> </p>
Overview
This tutorial demonstrates how to deploy an on-premises-style Active Directory environment using Azure Virtual Machines. It covers the setup of a Windows Server 2022 Domain Controller, a client machine (Windows 10), and the foundational networking and DNS configurations required to simulate a traditional on-prem domain within Azure.

📺 Video Demonstration
YouTube: How to Deploy On-Premises Active Directory within Azure Compute
(Step-by-step deployment guide including VM setup, domain creation, and domain joining.)

🧰 Environments and Technologies Used
Microsoft Azure – Virtual Machines (Compute)

Remote Desktop Protocol (RDP)

Active Directory Domain Services (AD DS)

PowerShell – for scripting and automation

🖥️ Operating Systems Used
Windows Server 2022 (Domain Controller)

Windows 10 (21H2) (Domain-joined client)

🌀 High-Level Deployment Steps
Provision two VMs in Azure (one Server 2022, one Windows 10)

Set static private IP on the Server VM and configure DNS

Install and configure Active Directory Domain Services

Join the client VM to the domain

🏗️ Deployment and Configuration Steps
1️⃣ Provision Virtual Machines and Set Up Networking
<p align="center"> <img src="https://i.imgur.com/DJmEXEB.png" width="80%" alt="Provision VMs"/> </p>
Two VMs are created within the same Azure Virtual Network (VNet). The server VM will act as the domain controller.

2️⃣ Promote Server to Domain Controller
<p align="center"> <img src="https://i.imgur.com/DJmEXEB.png" width="80%" alt="Promote to DC"/> </p>
Install the AD DS role via Server Manager or PowerShell, then promote the server to a Domain Controller with a new forest (e.g., corp.local).

3️⃣ Configure DNS and IP Settings
<p align="center"> <img src="https://i.imgur.com/DJmEXEB.png" width="80%" alt="DNS Settings"/> </p>
Update the network adapter on the client VM to use the server's private IP as its DNS. This ensures proper name resolution during the domain join.

4️⃣ Join Client to Domain
<p align="center"> <img src="https://i.imgur.com/DJmEXEB.png" width="80%" alt="Join Domain"/> </p>
From the Windows 10 VM, use System Properties to join the domain (e.g., corp.local). Reboot and log in with domain credentials.

✅ Summary
This project simulates an on-premises Active Directory environment within the Azure cloud, demonstrating:

AD DS role configuration on Windows Server 2022

DNS configuration and IP address planning in Azure

Domain joining a Windows 10 VM in the same VNet

Basic AD management and connectivity validation
