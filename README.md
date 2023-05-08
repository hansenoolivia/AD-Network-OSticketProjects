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
-Provided below is the link you will need in order to download each step from the Installation files-
https://docs.google.com/document/d/12QH7yrsaiUfYNOgZK7KgTSZQSJ-HYTSVcGFildWMRig/edit#
</p>
<br />

- Install / Enable IIS in Windowns with CGI 
- Install PHP Manager for IIS 
- Install Rewrite Module
- Create the directory C:\PHP
- Install PHP 7.3.8 and unzip the contents into C:\PHP
- Download and Install C++ Redistributable
- Download and Install MySQL 5.5.62
- Open IIS as an Admin & Register PHP from within IIS


<h2>Installation Steps</h2>
Step 1 - Installing and Enabling Information Internet Services on Windows with CGI
 
<p>
<img src="https://i.imgur.com/y6SuxGq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
IIS: Internet Information Services - Web server that allows this computer to serve up websites. 

Right click start menu, click run, type control for control panel, under programs, click turn windows features on / off,
click and expand Information Internet Services, expand world wide web services, expand application development features, click CGI (CGI lets us install PHP Manager), 
Install.

Test web sever: Type 127.0.0.1 into URL search bar, it should load IIS Default Website. 
</p>
<br />

Step 2 - From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
<p>
<img src="https://i.imgur.com/G9lgwnZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download PHP from installation files to computer, open downloads folder and double click to install, hit next, I agree, close app. Next we will download and install the Rewrite Module.
</p>
<br />

Step 3 - From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
<p>
<img src="https://i.imgur.com/AX4ClvR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download Rewrite Module, open downloads folder, double click to install, finish. 
</p>
<br />

Step 4 - Create the directory C:\PHP
<p>
<img src="https://i.imgur.com/M5FdBHO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Type C: into File Explorer search bar, right click under existing folders above and choose New, Folder, and type PHP, click enter). 
</p>
<br />

Step 5 - From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
 
<p>
<img src="https://i.imgur.com/3lCESBz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once downloaded, right click on file, extract all, when it wants destination, click browse, This PC, windows(C:), PHP folder, select and click extract. 

</p>
<br />

Step 6 - Download and Install C++ Redistributable
 
<p>
<img src="https://i.imgur.com/9zRU2Xs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once downloaded, double click on file, Agree to terms and conditions and install, close. 

</p>
<br />

Step 7 - Download and Install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
 
<p>
<img src="https://i.imgur.com/T2O8XkP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Double click mysql file once downloaded, click next, I accept agreement, typical install, install, 
make sure Launch the MySQL Instance Configuration Wizard is checked, finish.

Open notepad and write down credentials so you dont forget! 
Click next, choose standard configuration, next. Fill out username and password of choice, next, execute, Finish.


</p>
<br />

Step 8 & 9 - Open IIS as an Admin & Register PHP from within IIS
 
<p>
<img src="https://i.imgur.com/wUXi66Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/MzaBYy0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/PesIWbu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Click start, type IIS, right click Internet Information Services and run as administrator. 
Register PHP now, click PHP manager app, double click, PHP is not enabled so we need to register new PHP version, browse to where we put all the PHP files. 
C drive, PHP, click PHP.cgi (PHP executable), click open. 

*Anytime you do anything to IIS, it is recommended that you restart the web server, To do this click name of server at the top left and then go to Restart that is on top right of page*

</p>
<br />

<h2>Installing os Ticket</h2>
 </p>
 <p>
 
First - Download osTicket from the Installation Files Folder & Extract and copy “upload” folder to c:\inetpub\wwwroot

Find osTicket file (zip file) under downloads, double click, we want to drag the uploads file into a separate folder to 
c: \intetpub\wwwroot. To do this we will open up separate file explorer, click This PC, Windows (C:), innetpub, wwwroot, 
now we can drag the upload folder into this wwwroot folder. 

Now, Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”. Once the upload file has processed into wwwroot, you
can right click the upload folder and click rename, type osTicket and hit enter. 

Reload IIS again and click Restart. 
<p>
<img src="https://i.imgur.com/kWb292F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/uXDpqdp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7z5EU9W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>


Now reopen IIS, click sites underneath web server name (top left), default web site, click osTicket, 
on the right, click browse, *80. This should open up os Ticket if it does not then it means you've made an error. 
You'll need to restart the lab over or try to find where you went wrong along the way. 

os Ticket should open, *Note that some extensions are not enabled*

Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes.

<p>
<img src="https://i.imgur.com/LCxNNU8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/oW12QWu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DVSEFcQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5GHfrxY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BeXt5TD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/B1byKWa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<h2>Rename: ost-config.php</h2>
 
<p>
<img src="https://i.imgur.com/fDmaM4V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 
<img src="https://i.imgur.com/DmGfRFk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
 
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<p>
<br />
 
<h2>Assign Permissions: ost-config.php</h2>
 
Once you've changed the name to ost-config.php, you will need to assign permissions to ost-config.php. Right click and click Properties, Security, Advanced, Disable Inheritance, Choose "Remove all inherited permissions from this object". Add, select principal, enter "everyone" in object box. 
Click ok, Basic permissions: Full Control, Ok, Apply, Ok. 


</p>
<br />

<p>
<img src="https://i.imgur.com/Ic8Gtr3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/sWwcDPq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/tFHhqC4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7GhRy0O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/t98co4y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/c88A4sn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<br />
 
<h2>Continue Setting up osTicket in the browser (click Continue)</h2>
-From the Installation Files, download and install HeidiSQL-
<p>
<img src="https://i.imgur.com/3JMV4Fq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Install everything once done, create new connection to database, click new, 
username:root
password:Password1
These credentials should match the credentials you made during the MySQL setup.  


</p>
<br />

<h2>Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php</h2>
 
<p>
<img src="https://i.imgur.com/lfQHYLG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/U7gAM51.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<p>
 <br />
