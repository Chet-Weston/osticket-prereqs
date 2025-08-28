<p align="center">
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

<h2>List of Prerequisites</h2>

- Within the virtual machine, download the osTicket-Installation-Files.zip and unzip it onto the desktop. The folder should be called “osTicket-Installation-Files”
 The files in this folder are used to install osTicket and some of the dependencies.

- Install / Enable Internet Information Services (IIS) in Windows, along with CGI
World Wide Web Services -> Application Development Features -> enable CGI

- Install the Web Server (PHP Manager) from within the “osTicket-Installation-Files” folder (PHPManagerForIIS_V1.5.0.msi). Followed by installing the Rewrite Module (rewrite_amd64_en-US.msi). Create a new folder on the C drive and rename it PHP. Extract all PHP files into the new PHP folder on the C drive.
 

- From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi) and HeidiSQL to create the database. Rename to osTicket.  
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Set credentials 

- Open IIS as an Administrator... Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe). Reload IIS (Open IIS, Stop and Start the server)

- Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, rename “upload” to “osTicket”

- Install HeidiSQL for database configuration

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/XX3l96p.png" height="80%" width="80%" alt="Turn Windows Features On or Off"/>
</p>
<p>
Create an Azure Virtual Machine with Windows 10 & 4 CPUs. In the VM that we have just created, download the (osTicket-Installation-Files.zip) to your desktop and unzip the files. Make sure the file is named “osTicket-Installation-Files." As well as enabling Internet Information Services (IIS) in Windows, along with CGI. To do this from the Start menu, search for "Control Panel" and locate the "Programs" option; then, select "Turn Windows features on or off." Locate the option "Internet Information Services" and double-check that it's selected. From there, follow this path to enable CGI (Internet Information Services ---> World Wide Web Services ---> Application Development Features ---> [X] CGI. These steps are important to ensure that the web server is properly installed 
</p>
<br />

<p>
<img src="https://i.imgur.com/wQgHAz2.png" height="80%" width="80%" alt="Start and Stop IIS"/>
</p>
<p>
In your “osTicket-Installation-Files" folder, locate the "PHPManagerForIIS_V1.5.0.msi" file and install the program. As well as installing the "rewriteamd64_en-US.msi" module. After both have been installed successfully, go to your "C:" and create a folder called "PHP". Once that is created, go back into your “osTicket-Installation-Files" folder, right-click the "php-7.3.8-nts-Win32-VC15-x86.zip" and extract all into the new "PHP" folder we created on the "C:" drive. Once that has been extracted to your "PHP" folder, navigate back into the “osTicket-Installation-Files," locate and install both the "VC_redist.x86.exe" & "mysql-5.5.62-win32.msi" file. After "mysql-5.5.62-win32.msi" has been installed and launched, select the standard configuration setup and fill in the modified security settings with the desired "Root" password. From the start menu, search for "Internet Information Services" (IIS) and right-click and run as Admin. Register the "PHP" from within "IIS". Navigate to "PHP Manager" and locate the "Register new PHP version" and navigate back to the "PHP" folder we created on the "C:" in the folder, find the "php-cgi.exe" and select it as the new registered "PHP". Once that has been done, back in the "IIS" window, reload the "osticket-vm" by selecting the "Stop" and "Start" option. Navigate back to your “osTicket-Installation-Files" folder and extract the "osticket-v1.15.8" folder. Once that has been extracted, copy the newly unzipped files into the wwwroot folder located in the inetpub folder. (C: ---> inetpub ---> wwwroot) and rename the "upload" folder to "osTicket" ***double check that the file is named correctly*** Once that has been done, back in the "IIS" window, reload the "osticket-vm" by selecting the "Stop" and "Start" option.
</p>
<br />

<p>
<img src="https://i.imgur.com/onh4w1V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to Sites ---> default Web Site ---> osTicket on the right click "Browse *.80". Note that some of the extensions are not enabled to correct this. Go back to IIS ---> default ---> osTicket, double-click PHP manager, and click "Enable or disable an extension. and enable the following options (php_imap.dll, php_intl.dll & php_opcache.dll) once those have been enabled, refresh the osTicket site in your browser and observe the changes. After those options have been enabled, navigate back to your wwwroot folder. (C: ---> inetpub ---> osTicket ---> include ---> ost-sampleconfig.php) Here you are going to rename the "ost-sampleconfig.php" to "ost-config.php" ***This step is incredibly important, make sure the file is named correctly***. Right-click the newly renamed "ost-config.php" and select (properties ---> Securities ---> Advanced). Once in this window, select the option to "Disable inheritance - which removes all permissions. After they have been removed, add a new principal for this lab, we will have "everyone" and select access to be "Full control." 
</p>
<br />


<p>
<img src="https://i.imgur.com/aYM4IGz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Back into the osTicket installer, click continue, enter the chosen name of the helpdesk, and the default email. & create desired Admins. Once completed, navigate back to your “osTicket-Installation-Files" folder and install HeidiSQL. Once installed and opened. Create a new session with the same "User" & "Password" used in the installation section of the MySQL setup. Right-click "Unnamed" and create a new database named "osticket" ***make sure the name is correct***. Once the above steps have been completed, navigate back to the "osTicket installer" and finish setting up by filling out the database settings. Which should look like the example below. and install once complete. 
 <img src="https://i.imgur.com/RWpFhtu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
