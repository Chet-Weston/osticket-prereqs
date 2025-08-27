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
<img src="https://imgur.com/a/QeFJUk9" height="80%" width="80%" alt="Turn Windows Features On or Off"/>
</p>
<p>
Create an Azure Virtual Machine with Windows 10 & 4 CPUs. In the VM that we have just created, download the (osTicket-Installation-Files.zip) to your desktop and unzip the files. The file should be called “osTicket-Installation-Files." As well as enabling Internet Information Services (IIS) in Windows, along with CGI. From the Start menu, search for "Control Panel" and locate the "Programs" option; then, select "Turn Windows features on or off." Locate the option "Internet Information Services" and make sure it's selected. From there, follow this path to enable CGI (Internet Information Services ---> World Wide Web Services ---> Application Development Features ---> [X] CGI. These steps are important to ensure that the web server is properly installed 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
