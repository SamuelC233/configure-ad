<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployment in Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Active Directory Domain Services


<h2>Operating Systems Used </h2>

- Domain Controller Virtual Machine (dc-1) Windows Server 2022
- Client 1 Virtual Machine (client-1)Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory
- Create a Domain Admin User within the domain
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%201.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here are two virtual machines I created before the lab starts. The machine running windows server 2022 (dc-1) will be our primary focus point.
</p>
<br />


<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%202.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Start up Remote Desktop Connection and Enter the public IP address of dc-1.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%203.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enter the credentials for your virtual machine, press ok.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%204.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Server Manager dashboard, click “Add Roles and Features” to begin the setup wizard.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%205.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Next to continue.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%206.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Next once more to continue.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%207.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Verify that the domain controller (dc-1) appears in the list.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%208.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable “Active Directory Domain Services” by selecting the checkbox.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%209.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select “Add Features,” and proceed by clicking Next.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2010.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Next on each screen until you arrive at the “Confirmation” step.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2011.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select “Restart the destination server automatically if required,” and click “Install” to begin the installation.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2012.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On the Server Manager Dashboard, click the flag in the upper-right corner, followed by “Promote this server to a domain controller.”
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2013.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select “Add a new forest,” type “mydomain.com” for the Root domain name, and click Next.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2014.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a password, then re-enter it to confirm.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2015.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Uncheck “Create DNS delegation,” and continue clicking Next until the Prerequisites Check appears.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2016.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click “Install.” By creating the forest, this computer (dc-1) will now be recognized as a domain controller. Once the computer restarts, you will need to log in using a domain user account, as all users are now part of the domain (mydomain.com).
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2017.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Since my username (labuser) is part of the domain (mydomain.com), you need to specify the domain name as shown in the picture above.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2018.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After logging in, click Start, open “Windows Administrative Tools,” and then select “Active Directory Users and Computers.”
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2019.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right-click “mydomain.com,” move your cursor over “New,” and select “Organizational Unit” from the submenu.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2020.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Two Organizational Units (OUs) will be created to help maintain an organized structure within Active Directory. The first OU is named _EMPLOYEES, and the second is _ADMINS. After creating the first Organizational Unit, click OK and repeat the procedure to create the second. Once both OUs have been created, right-click mydomain.com and select Refresh to update the directory view.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2021.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, click on _ADMINS, right-click within the right pane, hover over New, and choose User from the menu.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2022.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Fill in the user’s details and specify the User logon name, then click Next to proceed.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2023.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a password, and for lab purposes only, select “Password never expires.” Click Next, then click Finish.

Now that Jane Doe has been added to the _ADMINS Organizational Unit, she must be added to the Domain Admins group to grant her administrative privileges on the domain.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2024.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right-click on Jane Doe and choose Properties.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2025.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click the Members Of tab, then click Add.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2026.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Type “Domain Admins” in the field and click Check Names to verify. Once confirmed, click OK, then Apply, and finally OK. After completing these steps, log out of the session.
</p>
<br />

<p>
<img src="https://github.com/SamuelC233/configure-ad/blob/main/Screenshot%2027.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log back into dc-1 using the newly created admin account. Be sure to enter the username in the following format: mydomain.com\username.
</p>
<br />
