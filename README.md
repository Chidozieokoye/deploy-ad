<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Infrastructural Deployment in Azure</h1>
Are you looking to deploy Active Directory in Azure? This step-by-step tutorial will walk you through the entire process, from creating a virtual network to configuring a Domain Controller in the cloud. Whether you're an IT beginner or an aspiring system administrator, this guide makes it easy to follow and practical to implement!.<br />


<h2>Video Demonstration</h2>

https://youtu.be/wXTWp5gJG6E

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

1. Set Up an Azure Virtual Network (VNet)

2. Deploy a Virtual Machine (VM) for the Domain Controller

3. Install Active Directory Domain Services (AD DS)

4. Configure DNS & Network Settings

5. Create & Manage Active Directory Objects


<h2>Deployment and Configuration Steps</h2>

<h2>Set Up an Azure Virtual Network</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, an Azure Virtual Network (VNet) is created to provide a secure, isolated environment where all the Active Directory components can communicate. The VNet is configured with subnets to organize network traffic, and network settings such as IP address ranges, DNS servers, and security rules are defined to ensure smooth connectivity between resources. This setup acts as the foundation for deploying the Domain Controller (DC) and other necessary components.
</p>
<br />

<h2>Deploy a Virtual Machine</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, a Virtual Machine (VM) is deployed in Azure to act as the Domain Controller (DC) for Active Directory. The VM is configured with the necessary CPU, RAM, and storage to handle directory services. A static IP address is assigned to ensure stability, and RDP (Remote Desktop Protocol) access is enabled for management. This VM will later be used to install and configure Active Directory Domain Services (AD DS) to manage users, groups, and resources.
</p>
<br />

<h2>Install Active Directory Domain Services</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, Active Directory Domain Services (AD DS) is installed and promoted to a Domain Controller (DC) on the Virtual Machine (VM) in Azure. This enables the server to function as a Domain Controller (DC), allowing centralized management of users, computers, and security policies. The installation includes adding necessary features, configuring domain settings, and preparing the server for promotion to a fully functional domain environment.
</p>
<br />

<h2>Configure DNS & Network Settings</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, the DNS and network settings are configured to ensure proper communication within the domain. The Domain Controller (DC) needs a static IP address and must use itself as the primary DNS server to handle name resolution for Active Directory. This ensures that domain-joined devices can locate and authenticate with the DC properly.
</p>
<br />

<h2>Create & Manage Active Directory Objects</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, Active Directory objects such as users, groups, computers, and organizational units (OUs) are created and managed. These objects help organize and control access to resources within the domain. Administrators can define roles, set permissions, and enforce policies to maintain security and efficiency in the network.
</p>
<br />
