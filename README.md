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
 
 
 <h1></h1>
 <h1></h1>
 
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

- Install Active Directory
- Create an Admin and Normal User Account in AD
- Join Client-1 to your domain (mydomain.com)
- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users


<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/RROmb01.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Service Manager from start window -> Add roles and features -> Click Next, Next, make sure operating system is selected ->
Check Active Directory Domain Services box -> Next -> Install. 
</p>
<br />

<p>
<img src="https://i.imgur.com/Qnx8iIQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Close out roles and features -> Look at the top right at yellow flag -> Click on it and select Promote the Server to a Domain Controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/O5X0iDZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select Add new Forest -> enter mydomain.com -> click next -> create password -> continue to click next until you get to Install.

Log out and Restart Computer.
</p>
<br />

<p>
<img src="https://i.imgur.com/aJNG1o4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once logged back in -> Reopen Service Manager -> Click Tools at the top right -> Click Active Directory User and Computers -> 
</p>
<br />


<p>
<img src="https://i.imgur.com/beyne8l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Active directory through the start menu -> Click mydomain at the top left -> New -> Organazational Unit -> Type in _EMPLOYEES -> 
Click Ok -> now repeat these steps and create an organazational unit for _ADMINS.
</p>
<br />

<p>
<img src="https://i.imgur.com/bib3mTR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on _ADMINS folder -> right click in the empty space -> Click New -> Click User -> Fill out credentials and click Finish ->
New user should appear in _ADMINS folder now. Right click on new user made -> click Properties -> Add -> Type Domain -> Check names ->
Click Domain Names -> Apply -> Ok. 
</p>
<br />

<p>
<img src="https://i.imgur.com/ulQkvgi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
</p>
<br />

<h1></h1>
<h1></h1>

<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Observe ICMP Traffic
- Obersve SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic 
- Observe RDP Traffic

<h2>Actions and Observations</h2>

<h3>Oberserve ICMP Traffic</h3>

<p>
<img src="https://i.imgur.com/etSDpoh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 
  
Use Remote Desktop to connect to your Windows 10 Virtual Machine -> Within your Windows 10 Virtual Machine -> Install Wireshark ->
Open Wireshark and filter for ICMP traffic only.
  
<p>
<img src="https://i.imgur.com/cQqUzJw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 
 
 <p>
<img src="https://i.imgur.com/HPvWURu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>   

Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM ->
Observe ping requests and replies within WireShark.
  
<p>
<img src="https://i.imgur.com/2PvBLsj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 

From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) -> observe the traffic in WireShark ->
Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM.
  
 <p>
<img src="https://i.imgur.com/c8hhOa3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic ->
Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity.
  
<p>
<img src="https://i.imgur.com/yE8oNuz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using ->
Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working) -> 
Then stop the ping activity.

<p>
<img src="https://i.imgur.com/SK6tIDZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<br />
  
<h2>Observe SSH Traffic</h2>
<p>
  
<p>
<img src="https://i.imgur.com/8LaXORS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Back in Wireshark, filter for SSH traffic only.


From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address) ->
Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark.
  
<p>
<img src="https://i.imgur.com/bkkUWTy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>  
Exit the SSH connection by typing ‘exit’ and pressing [Enter].
  
<br />
  
<h2>Observe DHCP Traffic</h2>
<p>
  
 <p>
<img src="https://i.imgur.com/8MCZp4Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://i.imgur.com/NRSDRL1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>  

Back in Wireshark, filter for DHCP traffic only.


From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)
Observe the DHCP traffic appearing in WireShark.
<br />
  
<h2>Observe DNS Traffic</h2>
<p> 
   
<p>
<img src="https://i.imgur.com/v0LAtXZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>  

Back in Wireshark, filter for DNS traffic only.


From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are ->
Observe the DNS traffic being show in WireShark.
<br />
  
<h2>Observe RDP Traffic</h2> 
<p>
  
<p>
<img src="https://i.imgur.com/s07S72o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 
  
Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)


Oserve the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted.
  
<br />  
<p>
  
*Lab Cleanup (DON’T FORGET THIS)*
  
- Close your Remote Desktop connection
- Delete the Resource Group(s) created at the beginning of this lab
- Verify Resource Group Deletion
  
  <br />
  <h1></h1>
