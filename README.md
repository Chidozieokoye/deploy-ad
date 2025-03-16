<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Infrastructural Deployment in Azure</h1>
In this lab, I started by creating an Azure Virtual Network (VNet), which acts as a private cloud network, allowing multiple resources like virtual machines (VMs) to communicate securely. Within this VNet, I deployed a virtual machine called DC-1 to serve as the Domain Controller. The domain controller is responsible for handling user authentication, domain-join requests, and DNS resolution. I also deployed a second virtual machine, Client-1, running Windows 10, within the same VNet. This VM simulates a client machine that will rely on the domain controller for network services.

To ensure reliable communication, I configured the DC-1 virtual machine’s Network Interface Card (NIC) with a static private IP address. This ensures that the IP address remains consistent over time, which is important for services like DNS resolution and domain joining. On Client-1, I adjusted the DNS settings to point to DC-1’s static private IP address, enabling it to resolve domain-related queries by contacting DC-1.

After completing these configurations, I logged into Client-1 and ran a ping command to test connectivity to DC-1’s static private IP address. A successful ping confirmed that Client-1 could communicate with DC-1 over the VNet, ensuring that the network configuration, DNS resolution, and domain communication were working as expected. For a more detailed walkthrough, please check out the video demonstration below.<br />


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

2. Deploy a Virtual Machine for the Domain Controller Called DC-1

3. Deploy a Windows-10 Virtual Machine Called Client-1

4. Set Domain Controller’s NIC Private IP address to be static

5. Set Client-1’s DNS settings to DC-1’s Private IP address.

6. Login to Client-1 and attempt to ping DC-1’s private IP address


<h2>Deployment and Configuration Steps</h2>

<h2>Set Up an Azure Virtual Network</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, I created an Azure Virtual Network (VNet) to establish a secure and isolated environment where all the Active Directory components can communicate. I configured the VNet with subnets to help organize the network traffic and defined network settings, such as IP address ranges, DNS servers, and security rules, to ensure smooth connectivity between resources. This setup served as the foundation for deploying the Domain Controller (DC) and other necessary components.
</p>
<br />

<h2>Deploy a Virtual Machine for the Domain Controller Called DC-1</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, I deployed a virtual machine named DC-1 in Azure to serve as the domain controller. This VM is responsible for managing user authentication, enforcing security policies, handling directory services, and providing DNS resolution for the domain. It runs a Windows Server operating system with the Active Directory Domain Services (AD DS) role installed, which allows it to create and manage a domain where other devices, like client machines, can join and authenticate. As the domain controller, DC-1 becomes a central part of the network infrastructure, ensuring secure access and efficient management of resources.
</p>
<br />

<h2>Deploy a Windows-10 Virtual Machine Called Client-1</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, I deployed a virtual machine named Client-1 running Windows 10 in Azure to simulate a typical client machine within the network. This VM will be used to test and demonstrate how client devices interact with the domain controller for services like authentication, DNS resolution, and network resource access. I configured the client machine to join the domain managed by the domain controller, allowing it to rely on the DC for directory services and security policies.
</p>
<br />

<h2>Set Domain Controller’s NIC Private IP address to be static</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, I set the Domain Controller's Network Interface Card (NIC) private IP address to static. This ensures that the IP address remains consistent over time, providing a reliable connection for network communication, DNS resolution, and other services that depend on the Domain Controller. By doing this, I make sure that there are no disruptions in connectivity with client machines and that services like Active Directory and DNS continue to function properly without any issues caused by IP address changes.
</p>
<br />

<h2>Set Client-1’s DNS settings to DC-1’s Private IP address.</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, I configured Client-1's DNS settings to use DC-1’s private IP address. This ensures that Client-1 queries the Domain Controller for DNS resolution. By doing this, Client-1 can resolve domain names, authenticate users, and access network resources by relying on the domain controller’s DNS services. This setup is crucial for proper communication and functionality within the domain, allowing the client machine to find and interact with the domain controller for directory services and other domain-related tasks.
</p>
<br />

<h2>Login to Client-1 and attempt to ping DC-1’s private IP address</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this step, I logged into Client-1 and opened PowerShell to use the Test-Connection command (also known as the ping command) to test the network connectivity between Client-1 and DC-1 by pinging DC-1’s private IP address. This step helps verify that Client-1 can successfully reach DC-1 over the network, confirming that the DNS settings are correct and that the client can communicate with the domain controller for authentication, directory services, and other domain-related functions. If the ping is successful, it confirms that the network configuration is correct and that both virtual machines are properly connected.
</p>
<br />
