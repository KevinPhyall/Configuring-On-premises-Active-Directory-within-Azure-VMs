
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
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

- Step 1 Create a Resource Group
- Step 2 Create a Virtual Network and Subnet
- Step 3 Create the Domain Controller VM (Windows Server 2022)
- Step 4 Set Domain Controller’s NIC Private IP address to be static
- Step 5 Disable the Windows Firewall
- Step 6 Create the Client VM (Windows 10) named
- Step 7 Attach it to the same region and Virtual Network as DC-1
- Step 8 Set Client-1’s DNS settings to DC-1’s Private IP address
- Step 9 Restart Client-1
- Step 10 Login to Client-1
- Step 11 Ping DC-1’s private IP address
- Step 12 Open PowerShell and run ipconfig /all


<h2>Deployment and Configuration Steps</h2>

<p>
<img width="678" alt="image" src="https://github.com/user-attachments/assets/95c30c1b-0cb2-4979-8ad3-69c632b458b0" />

</p>
<p>
Create a Resource Group
</p>
<br />

<p>
<img width="678" alt="image" src="https://github.com/user-attachments/assets/fed4d44e-2a79-470a-86a6-7dcd542ee6ff" />

</p>
<p>
Create a Virtual Network and Subnet
</p>
<br />

<p>
<img width="678" alt="image" src="https://github.com/user-attachments/assets/615fd6e0-3c57-4ed2-8aee-798ae363b9a9" />

</p>
<p>
Create the Domain Controller VM (Windows Server 2022) named “DC-1”
</p>
<br />

<p>
<img width="678" alt="image" src="https://github.com/user-attachments/assets/1d0f0519-2bec-4659-862d-37985d022096" />

</p>
<p>
After VM is created, set Domain Controller’s NIC Private IP address to be static
</p>
<br />

<p>
<img width="488" alt="image" src="https://github.com/user-attachments/assets/1a334b7a-570a-4916-8ab5-4d364ea3fd1d" />
<img width="505" alt="image" src="https://github.com/user-attachments/assets/78a2e95b-d63e-4fdd-afb7-a1a2dc7eca37" />
<img width="505" alt="image" src="https://github.com/user-attachments/assets/f6d19ab0-68a2-4610-9df2-837d4df879df" />

</p>
<p>
Log into the VM and disable the Windows Firewall
</p>
<br />

<p>
<img width="665" alt="image" src="https://github.com/user-attachments/assets/f89b0835-5903-4f64-81e8-ba0908c4cad7" />
<img width="665" alt="image" src="https://github.com/user-attachments/assets/f8d1af2f-db33-4ae0-a8db-5b4958f55d2f" />

</p>
<p>
Create the Client VM (Windows 10) named “Client-1”
</p>
<br />

<p>
<img width="665" alt="image" src="https://github.com/user-attachments/assets/d009f2e4-cfe0-468d-a1a6-bcb3d4090db2" />

</p>
<p>
After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address (copy private ip address>client 1>network>network settings>VNIC>DNS Server>Custom>Save
</p>
<br />

<p>
<img width="665" alt="image" src="https://github.com/user-attachments/assets/99f981d2-2519-4d87-a668-fddf276f901d" />
<img width="665" alt="image" src="https://github.com/user-attachments/assets/fb4a4996-1e5e-41a8-b85e-dde5795c479c" />

</p>
<p>
From the Azure Portal, restart Client-1
</p>
<br />

<p>
<img width="665" alt="image" src="https://github.com/user-attachments/assets/c30ee646-7b7e-4c14-91ed-9aee78dff9bd" />
<img width="665" alt="image" src="https://github.com/user-attachments/assets/2e4d39cc-8546-45b1-a24d-172ee779ac1b" />

</p>
<p>
Login to Client-1
Attempt to ping DC-1’s private IP address (obtain dc-1 ipaddress>power shell>ping + private ipaddress
* Ensure the ping succeeded
</p>
<br />

<p>
<img width="665" alt="image" src="https://github.com/user-attachments/assets/f795adc7-ed4e-4f39-af47-ffe62d1079a4" />

</p>
<p>
From Client-1, open PowerShell and run ipconfig /all
* The output for the DNS settings should show DC-1’s private IP Address
