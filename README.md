On-Premises Active Directory Deployed in the Cloud (Azure)
<p align="center"> <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo" width="300"/> </p>
📘 Overview
This project demonstrates how to deploy and configure an on-premises-style Active Directory Domain Services (AD DS) environment entirely within Microsoft Azure. The guide walks through provisioning virtual machines, promoting a domain controller, and joining a client machine to the new domain—all in a cloud-based lab environment.

📺 Video Demonstration
YouTube: How to Deploy On-Premises Active Directory within Azure Compute
(Complete step-by-step demonstration.)

🧰 Environments and Technologies Used
Microsoft Azure – Virtual Machines (Compute)

Remote Desktop (RDP)

Active Directory Domain Services (AD DS)

PowerShell – Used for some configuration and testing

🖥️ Operating Systems Used
Windows Server 2022 – Domain Controller

Windows 10 (21H2) – Domain-joined client

🚀 High-Level Deployment and Configuration Steps
Provision Azure Virtual Machines (one Server, one Client)

Configure Networking (same VNet, static IP for DC, DNS config)

Install AD DS on Server VM and promote to Domain Controller

Join Client VM to Domain

🛠️ Detailed Deployment and Configuration Steps
1️⃣ Provision Azure Virtual Machines
<img width="802" height="402" alt="image" src="https://github.com/user-attachments/assets/2f27da98-d1b4-4f89-a8a5-fd9f3d570e64" />

Create two Azure VMs:

One running Windows Server 2022 for AD DS

One running Windows 10 to act as a domain-joined client
Ensure both VMs are deployed in the same Virtual Network (VNet).

2️⃣ Configure Static IP and DNS for Server VM
<img width="2854" height="1556" alt="image" src="https://github.com/user-attachments/assets/5003ee8f-c790-4934-9cc1-1aab31dff3d4" />

Assign a static private IP to the Server VM in Azure networking.

Set the client VM’s DNS server to point to the private IP of the Server.
This allows the client to locate and communicate with the domain controller.

3️⃣ Install Active Directory Domain Services (AD DS)
<img width="807" height="522" alt="image" src="https://github.com/user-attachments/assets/7f738108-7953-4b05-9634-2cb94ccf05b2" />

Use Server Manager or PowerShell (Install-WindowsFeature AD-Domain-Services) to install the role.

Run the Active Directory Configuration Wizard to promote the server to a Domain Controller.

Create a new forest (e.g., corp.local).

4️⃣ Join Client VM to the Domain
<img width="796" height="564" alt="image" src="https://github.com/user-attachments/assets/9916494b-8149-4150-bd90-75bc8fc50d0d" />

Log into the Windows 10 VM via RDP.

Open System Properties > Change Settings > Domain and enter the domain name (e.g., corp.local).

Authenticate with a domain admin account, then restart.

✅ Summary
This lab successfully demonstrates:

Deployment of a functional Active Directory environment in Azure

Key concepts of on-prem domain simulation using cloud compute resources

Hands-on experience with network configuration, domain promotion, and client join process

This setup can be expanded with additional services like Group Policy, DHCP, DNS zones, or even Azure AD Connect for hybrid identity scenarios.
