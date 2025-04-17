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
Before proceeding with the installation, Internet Information Services (IIS) must be enabled, as it is a necessary component for running osTicket on a virtual machine (VM) hosted in Azure. To enable IIS, open the Control Panel, navigate to Programs, and select Turn Windows features on or off from the left-hand menu. In the Windows Features dialog, expand Internet Information Services, then expand Web Management Tools, and check IIS Management Console. Next, expand World Wide Web Services, followed by Application Development Features. Under this section, enable CGI, and click OK to apply the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/Q6wtGBk.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After enabling Internet Information Services (IIS), download and install PHP Manager (PHPManagerforIIS_V1.5.0.msi) from the installtion files folder. Then download and install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />

<p>
<img src="https://i.imgur.com/9kPWqbs.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the Rewrite Module has been installed, create a new directory named C:\PHP on the Windows (C:) drive. This directory will serve as the destination for extracting the contents of the PHP Manager 7.3.8 archive (php-7.3.8-nts-Win32-VC15-x86.zip) downloaded from the installation files. Unzip all files from the archive into the C:\PHP folder.
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
Next, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the provided installation files. During the setup process, accept the license agreement and choose the Typical installation option. Once the installation is complete, launch the MySQL Configuration Wizard. Select Standard Configuration, then ensure that Install As Windows Service is selected and that Launch the MySQL Server automatically is checked.
For the login credentials, use root as both the username and password. While these credentials are intentionally simple for the purposes of this lab, it is important to note that in a real-world environment, stronger and less predictable login details should be used to maintain security.
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
Before installing osTicket, certain configurations must be made within IIS. Start by opening Internet Information Services (IIS) as an administrator and navigating to PHP Manager. In PHP Manager, select Register new PHP version, then click Browse and locate the php-cgi.exe file inside the PHP folder created earlier in the lab. Once the PHP version has been successfully registered, reload the IIS server from within the management console to apply the changes. 
</p>
<br />

<p>
<img src="https://i.imgur.com/2u4beoc.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download osTicket v1.15.8 from the provided installation files. Once downloaded, extract the contents and copy the upload folder to the following directory: C:\inetpub\wwwroot. Inside the wwwroot folder, rename the upload folder to osTicket. After completing these steps, reload the IIS server to apply the changes.
  <p>
<img src="https://i.imgur.com/3hzyBJE.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  <p>
<img src="https://i.imgur.com/G4tReb1.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the IIS console, navigate to Sites > Default Web Site > osTicket. Click "Browse *:80" to launch the osTicket installation page in your default web browser. At this point, you may notice that some required PHP extensions are not yet enabled. These will need to be activated before proceeding with the installation.To enable the necessary extensions, ensure you're still within the osTicket section in IIS and open PHP Manager. Click on "Enable or disable an extension", then enable the following PHP extensions: php_imap.dll, php_intl.dll, and php_opcache.dll.
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
Before continuing to install osTicket, a file needs to be renamed as well as have its permissions changed. From C:\inetpub\wwwroot\osTicket\include, rename ost-sampleconfig.php to ost-config.php. The newly named ost-config.php will have its permissions changed. Open its Properties and change the following permissions: Disable inheritence -> Remove All and New Permissions -> Everyone -> All.
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
From the installation files, download and install HeidiSQL. Create a new session with HeidiSQL and enter the password used in the installation of MySQL earlier. Within the new session, right-click on Unnamed and create a new database named osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/0qu3z2V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Within osTicket browser window, enter the necessary details to set up osTicket. For the MySQL database, use the credentials used for MySQL and HeidiSQL.

<p>
<img src="https://i.imgur.com/X9RlHQY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
