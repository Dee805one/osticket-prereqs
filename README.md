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
Before proceeding with the osTicket installation, a configuration file must be renamed and its permissions updated. Navigate to C:\inetpub\wwwroot\osTicket\include and rename the file ost-sampleconfig.php to ost-config.php.

Once renamed, right-click on ost-config.php and select Properties. Under the Security tab, make the following changes:

1. Click Disable inheritance and choose Remove all inherited permissions from this object.
2. Click Add, enter Everyone as the user/group, and assign Full control permissions.
These changes ensure that osTicket has the appropriate access needed during installation.
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
Download and install HeidiSQL from the provided installation files. Once installed, launch HeidiSQL and create a new session. In the session settings, enter the password you used during the MySQL installation. After connecting, right-click on Unnamed in the left-hand panel and select Create new > Database. Name the new database osTicket, then click OK to confirm.
</p>
<br />

<p>
<img src="https://i.imgur.com/0qu3z2V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Within the osTicket installation page in your browser, fill in the required details to complete the setup process. This includes configuring the system settings, admin user account, and database information. For the MySQL database section, use the same credentials that were set up earlier for MySQL and HeidiSQL—specifically, the username and password you configured during the MySQL installation.

<p>
<img src="https://i.imgur.com/X9RlHQY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once osTicket has been successfully installed, a few post-installation cleanup steps are required before using the application.

First, delete the setup folder located at C:\inetpub\wwwroot\osTicket. Then, navigate back to C:\inetpub\wwwroot\osTicket\include and modify the permissions for the ost-config.php file. At this point, the file should no longer have Full Control permissions granted to Everyone. Update the permissions so that the file is set to Read-only access.

These steps help secure your osTicket installation and prevent unauthorized modifications.
</p>
<br />
