<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Infrastructure in Azure (Virtual Machine) for Windows Users</h1>
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

- Setup Remote Desktop for non-administrative users
- Create additional users
  
<h2>Setup Remote Desktop for non-administrative users</h2>

Log into Client-1 as mydomain.com\jane_admin, using credentials you previously created
<p align left>
<img width="302" height="185" alt="image" src="https://github.com/user-attachments/assets/70390a6e-8dec-48d3-89ee-650ef4184ea9" />
<img width="336" height="323" alt="image" src="https://github.com/user-attachments/assets/709ea71d-2618-4ed3-8889-f515695c805f" />
<img width="287" height="300" alt="image" src="https://github.com/user-attachments/assets/5671c9f6-fb87-4175-b79f-2153091195c4" />

Open system properties (right click on start), from the right menu click on “Remote Desktop”
<p align left>
<img width="512" height="287" alt="Screenshot 2025-12-01 111557" src="https://github.com/user-attachments/assets/55c358ff-5856-4aef-a36a-be0b09f72007" />

In Remote Desktop, scroll down to User Accounts and click on Select user that can remotely access this PC
<p align left>
<img width="499" height="374" alt="Screenshot 2025-12-01 111853" src="https://github.com/user-attachments/assets/c9346d1a-d1b6-459a-b547-c5fcff13a043" />

Click on Add, and then type Domain Users, click on Check Names, click in Ok, and finally by default all domain users will be able to use Remote Desktop 
<p align left>
<img width="335" height="296" alt="Screenshot 2025-12-01 112550" src="https://github.com/user-attachments/assets/37e8f577-7b95-4983-93ee-2ae32e35468a" />
<img width="406" height="224" alt="Screenshot 2025-12-01 112900" src="https://github.com/user-attachments/assets/0becec56-4468-458a-a265-8cc5050e8254" />
<img width="337" height="305" alt="Screenshot 2025-12-01 113154" src="https://github.com/user-attachments/assets/76a43eb5-3fae-4537-967c-93bd50edd62b" />

<h2>Create additional users</h2>

Create a bunch of additional users and attempt to log into client-1 with one of the users. In dc-1 open PowerShell_ise as an administrator 
<p align left>
<img width="208" height="143" alt="image" src="https://github.com/user-attachments/assets/245f4044-cdb2-44ea-9b49-d98565b37dc0" />

Click on New, Create a new File and paste the contents of the script [into it ](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1)
<p align left>
<img width="1440" height="799" alt="image" src="https://github.com/user-attachments/assets/2a71dc1e-a7e0-498c-ae89-a8178ac89185" />

Saved the file named: create-users in your Desktop, copy and paste the script
<p align left>
<img width="492" height="371" alt="Screenshot 2025-12-01 114841" src="https://github.com/user-attachments/assets/336b823a-dec6-45c2-ae8d-7abf8e5ff5e2" />
<img width="1421" height="776" alt="image" src="https://github.com/user-attachments/assets/7a70c45e-e765-4798-8b39-e6c93dd8e19b" />

Run the script and observe the accounts being created
<p align left>
<img width="986" height="928" alt="image" src="https://github.com/user-attachments/assets/40e3bbe5-eb12-463c-be2b-c8b246e65c38" />

When finished, open ADUC and observe the accounts in the appropriate OU　(_EMPLOYEES)
<p align left>
<img width="922" height="761" alt="image" src="https://github.com/user-attachments/assets/43ad87a2-bf1d-47f9-8cdb-7f7d0213f7b9" />

attempt to log into Client-1 with one of the accounts (take note of the password in the script)
<p align left>
<img width="499" height="244" alt="Screenshot 2025-12-01 120131" src="https://github.com/user-attachments/assets/ada2668b-88e6-4784-8172-dda1b9584448" />
<img width="290" height="305" alt="image" src="https://github.com/user-attachments/assets/730baf84-fcc3-43a2-9aef-5d3f646c35b3" />
<img width="516" height="274" alt="Screenshot 2025-12-01 122202" src="https://github.com/user-attachments/assets/ed5755aa-e31f-4e49-af52-e9e39cabbc1e" />


# active-directory-users
