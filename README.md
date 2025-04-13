# osticket-prereqs<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Azure Virtual Machine

<h2>List of Prerequisites</h2>

- VM with Remote Desktop
- Enable IIS in Windows WITH CGI
- PHP Manager
- MySQL
- HeidiSQL

<h2>Installation Steps</h2>

<p>
<img ![Screenshot 2025-04-12 at 1 24 18 PM](https://github.com/user-attachments/assets/db2ccdd5-a1fe-4afb-b973-8b677cab95c9)

</p>
<p>

<p>
<img src="https://i.imgur.com/TqJTb1K.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before installing any files, Internet Information Services (IIS) needs to be enabled. We are installing osTicket on a virtual machine (VM) using Azure and it needs IIS in order to function. To turn on IIS, open the Control Panel. From the Control Panel, open Programs and on the left hand side click on Turn Windows Features On or Off. Within this menu, expand Internet Information Services, expand Web Management Tools and enable IIS Management Console. Click and expand World Wide Web Services and expand Application Development Features. In Application Development Features, enable CGI and click ok to confirm.
</p>
<br />

<p>
<img src="https://i.imgur.com/Q6wtGBk.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After enabling IIS, download and install PHP Manager for IIS (PHPManagerforIIS_V1.5.0.msi) from the installtion files folder. Download and install the Rewrite Module (rewrite_amd64_en-US.msi) after installing PHP Manager for IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/9kPWqbs.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After installing the Rewrite Module, create a new folder called C:\PHP on the Windows (C:) drive. This folder will be used to unzip the files from the PHP Manager 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) folder downloaded from the installation files. Extract all contents from the zip folder into the C:\PHP folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/Zb7OqyC.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Download and install VC_redist.x86.exe from the installation files.
  <p>
<img src="https://i.imgur.com/z3i9cq6.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/oNXgskI.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/TjJeME0.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files. Within the MySQL setup wizard, click "I agree" and select a Typical install. Launch the Configuration Wizard after the installation. Then Select Standard Configuration and select Install As Windows Service and make sure Launch the MySQL Server automatically is checked. For credentials, the username will be root and the password is also root. In a practical setting, the credentials will not be basic to where they can be easily guessed, but for the purposes of this lab, the standard credentials root and root will do.
</p>
<br />

<p>
<img src="https://i.imgur.com/rCa6uAP.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/fsNzdnE.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/NcdfwQp.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before installing osTicket, configurations need to be made within IIS. Open IIS as an admin and select PHP Manager. Within PHP Manager, select Register a new PHP version. Select Browse and select the PHP CGI file within the PHP folder created earlier in the lab. After registering the PHP version, reload the IIS server within the management console.
</p>
<br />

<p>
<img src="https://i.imgur.com/2u4beoc.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/3hzyBJE.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/G4tReb1.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/mKiBd8a.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  <p>
<img src="https://i.imgur.com/NQp2CyX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/gTkzdoM.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/LLNnrz3.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/X9RlHQY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
