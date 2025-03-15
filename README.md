<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Infrastructural Deployment in Azure</h1>
This setup begins by creating an Azure Virtual Network (VNet), which serves as a private cloud network allowing multiple resources, like virtual machines (VMs), to communicate securely. Within this VNet, a virtual machine called DC-1 is deployed to act as the Domain Controller. The domain controller is responsible for managing user authentication, domain-join requests, and DNS resolution. A second virtual machine, Client-1, running Windows 10, is also deployed within the same VNet, simulating a client machine that will rely on the domain controller for network services.


To ensure reliable communication, the DC-1 virtual machine’s Network Interface Card (NIC) is configured with a static private IP address, ensuring its IP address doesn’t change over time. This consistency is crucial for services like DNS resolution and domain joining. On Client-1, the DNS settings are adjusted to point to DC-1’s static private IP address. This enables Client-1 to resolve domain-related queries by contacting DC-1 for DNS resolution.


Once these configurations are completed, a login is performed on Client-1, and a ping command is issued to test connectivity to DC-1’s static private IP address. If the ping is successful, it confirms that Client-1 can communicate with DC-1 over the VNet, indicating that the network configuration, DNS resolution, and domain communication are functioning as expected.
.<br />


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
In this step, an Azure Virtual Network (VNet) is created to provide a secure, isolated environment where all the Active Directory components can communicate. The VNet is configured with subnets to organize network traffic, and network settings such as IP address ranges, DNS servers, and security rules are defined to ensure smooth connectivity between resources. This setup acts as the foundation for deploying the Domain Controller (DC) and other necessary components.
</p>
<br />

<h2>Deploy a Virtual Machine for the Domain Controller Called DC-1</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A virtual machine named DC-1 is deployed in Azure to serve as the domain controller, which is responsible for managing user authentication, enforcing security policies, handling directory services, and providing DNS resolution for the domain. This VM runs a Windows Server operating system with the Active Directory Domain Services (AD DS) role installed, enabling it to create and manage a domain where other devices, such as client machines, can join and authenticate. The domain controller becomes a central part of the network infrastructure, ensuring secure access and management of resources.
</p>
<br />

<h2>Deploy a Windows-10 Virtual Machine Called Client-1</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A virtual machine named Client-1 running Windows 10 is deployed in Azure to simulate a typical client machine within the network. This VM will be used to test and demonstrate how client devices interact with the domain controller for services like authentication, DNS resolution, and network resource access. The client machine will be configured to join the domain managed by the domain controller and will rely on it for directory services and security policies.
</p>
<br />

<h2>Set Domain Controller’s NIC Private IP address to be static</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The Domain Controller's Network Interface Card (NIC) private IP address is set to static to prevent it from changing over time, ensuring a consistent and reliable IP address for network communication, DNS resolution, and other services that rely on the Domain Controller. This is important for maintaining connectivity with client machines and ensuring that services like Active Directory and DNS continue to function properly without interruption due to IP address changes.
</p>
<br />

<h2>Set Client-1’s DNS settings to DC-1’s Private IP address.</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Client-1's DNS settings are configured to use DC-1’s private IP address, ensuring that the client machine queries the Domain Controller for DNS resolution. This allows Client-1 to resolve domain names, authenticate users, and access network resources by relying on the domain controller’s DNS services, which are essential for proper communication and functionality within the domain. This setup ensures that the client machine can find and interact with the domain controller for directory services and other domain-related tasks.
</p>
<br />

<h2>Login to Client-1 and attempt to ping DC-1’s private IP address</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You log in to Client-1 and open PowerShell to use the Test-Connection command (or the ping command) to ping DC-1’s private IP address, testing the network connectivity between the client machine and the domain controller. This step verifies that Client-1 can successfully reach DC-1 over the network, ensuring that the DNS settings are correct and that the client can communicate with the domain controller for authentication, directory services, and other domain-related functions. If the ping is successful, it confirms proper network configuration and connectivity between the two virtual machines.
</p>
<br />
