<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory
- Promote the Domain Controller
- Create a Domain Admin User
- Join Client-1 to the Domain

<h2>Deployment and Configuration Steps</h2>

![image](https://github.com/user-attachments/assets/d0436f63-9add-4710-9245-80de4ba4a095)

- Login to DC-1 and install Active Directory Domain Services
- Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
- Restart and then log back into DC-1 as user: mydomain.com\labuser

<br />

![image](https://github.com/user-attachments/assets/3cd5baaf-cb16-4b5b-bac5-f8a8eddd8bbc)

- In Active Directory Users and Computers (ADUC), create two Organizational Units (OUs): _EMPLOYEES and _ADMINS.
- Create a new employee user (Jane Doe) with the username jane_admin, and add the user to the Domain Admins security group.
- Log out and log in as mydomain.com\jane_admin, using this account for administrative tasks moving forward.
  
<br />

![image](https://github.com/user-attachments/assets/faba9464-fe06-476d-b22c-7edd58d019c9)

- Configure Client-1's DNS settings in the Azure Portal to point to the DC's private IP address.
- Restart Client-1 and log in as the original local admin (labuser).
- Join Client-1 to the domain (mydomain.com), restart the machine, and verify that Client-1 appears in ADUC.
- Create a new OU called _CLIENTS and move Client-1 into this OU for organization.
<br />
