<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Welcome to this osTicket tutorial! Here, we will outline the prerequisites and installation of the open-source help desk ticketing system.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Enable IIS (Internet Information Services) in Windows with CGI (Common Gateway Interface)
- Install PHP Manager for IIS
- Install Rewrite Module
- Install Visual C++ Redistributable
- Install MySQL
- Install HeidiSQL

<h2>Installation Steps</h2>
<h3>1. Create a Windows 10 Virtual Machine via Microsoft Azure</h3>
 
   - Go to Microsoft Azure Portal, click the search bar, type virtual machines and click Virtual Machines.
    
![1](https://github.com/user-attachments/assets/aeb35abd-77df-46e3-a2ba-c30ebc7e75e7)

<br />
 
   - On the Virtual Machines page, click create and choose Virtual Machine. (You can also use the blue create button near the center of the page.)
    
![Screenshot 2025-06-24 161911](https://github.com/user-attachments/assets/84663978-487e-4357-b5c5-453b74c2ed75)

<br />

 - On Virtual Machine Name, type in osTicket-vm (Azure will create a resource group by default if you haven't created one)
 - Region will depend on your location and will be set automatically (if not, set it to your region)
 - Scroll down to the next section
    
![Screenshot 2025-06-24 162533](https://github.com/user-attachments/assets/14deba80-423e-479b-8365-83ee894b28b0)

<br />

 - For Image, choose Windows 10 Pro, version 22H2
 - For Size, choose at least 4 vcpus to ensure a smooth performing VM
 - Fill in your own username and password (this will be used to log into the VM) 
    
![Screenshot 2025-06-24 164910](https://github.com/user-attachments/assets/f6815f87-e935-41de-a32f-3db170f27b42)

<br />

 - At the end of the page, make sure to click the check box, "I confirm I have an eligible Windows 10/11 license"
 - Click Review + Create
    
![image](https://github.com/user-attachments/assets/7c8fb079-e17d-45a9-9388-33f6c62d93f9)

<br />

 - Give it a second to load and validate everything. Once it is passed, click create.
    
![image](https://github.com/user-attachments/assets/b89d1f77-bdf7-42ab-b9db-5854ba4b97d8)

<br />

 - After creating the virtual machine, wait until your deployment is complete.
    
![image](https://github.com/user-attachments/assets/6d8a30d7-fb9f-4f2b-9f2d-f8440ae2b137)

<br />

![image](https://github.com/user-attachments/assets/08bc2b6a-59f5-4962-900d-e8a035f8a6f6)

<br />

<h3>2. Log in to your VM using Remote Desktop</h3>

 - To open Remote Desktop, press Windows Key or click on the start button , type Remote Desktop and click Remote Desktop Connections.

![image](https://github.com/user-attachments/assets/bb37d1ab-456a-4fea-af52-66b6a38cfecd)

<br />

- Once you open Remote Desktop Connections, you will need to fill in the IP address of your VM.

![image](https://github.com/user-attachments/assets/1675bf49-1db2-42f0-9cb9-a4c9e1aa5241)

<br />

- To obtain your VM's IP address, go back to Microsoft Azure Portal and you should see your VM listed and click.
- Alternatively, you can also click Virtual Machines / Use the search box, type virtual machine and click Virtual Machines.

![image](https://github.com/user-attachments/assets/6f3e5323-26fd-4a3e-b409-e8fea6316bea)

<br />

 - You can find your VM's IP address two ways. Either way, copy the IP address and paste it onto Remote Desktop Connections.
    - The first picture will show you where if you clicked Virtual Machines.
    - The second picture will show you if you clicked on your VM listed on the Azure Portal.

![image](https://github.com/user-attachments/assets/922187d7-3c56-412a-b873-a8d7c3a18633)

![image](https://github.com/user-attachments/assets/9ef3c450-295f-45a0-a1c8-e5539881a7f0)

![image](https://github.com/user-attachments/assets/fe02a4d8-23a5-46ed-9425-8f99bf80c229)

<br />

 - Click show options, fill in the Username you created with your VM and click connect.

![image](https://github.com/user-attachments/assets/3f3c2c68-36d2-40dd-8e19-9b48692a344c)

<br />

 - Fill in the password you created with your VM and click OK.

![image](https://github.com/user-attachments/assets/b21b8b1f-ce64-4f3b-9b7c-29b4b2cff153)

<br />

 - Inside the VM , download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip the folder.
  - To download, click the link above, click download anyway and wait for it to finish downloading. Once it's done, click the file to open.

![image](https://github.com/user-attachments/assets/bcf8318f-a8b7-4a31-8ead-08d7c056eb89)

<br />
  
  -  By default, it should go to your downloads folder, left click osTicket-Installation-Files , choose extract all and click extract.
  -  After extracting, you should have 2 files. 1 zip folder and a regular folder with the same names. You can delete the zip folder if you want.

![image](https://github.com/user-attachments/assets/ef6ebf85-c58f-4f36-a58f-f3fdb9ecf9e1)

![image](https://github.com/user-attachments/assets/39ccdc0d-e8c3-4d25-9b1d-5a5c1336db6c)

![image](https://github.com/user-attachments/assets/2524255b-3458-4c9f-81f5-577a7143de6e)

<br />

<h3>3. Install / Enable IIS in Windows WITH CGI</h3>
     
- To enable IIS with CGI, press windows key, type Control Panel and click

![image](https://github.com/user-attachments/assets/7fefe0b9-757e-4c2f-a87c-6574e6d0d119)
 
<br />
 
 - Within Control Panel, click Programs

![image](https://github.com/user-attachments/assets/b2db613b-b49c-4a2c-b7fe-fdaca4ba62b1)

<br />
 
 - Under Programs and Features, click Turn Windows Features on or off

![image](https://github.com/user-attachments/assets/5a357d23-5ae1-4f7e-bf08-9b77e2dd0655)

<br />
 
 - Within Windows Features, look for/click Internet Information Services  > look for/click Application Development Features > look for/ click CGI checkbox and click OK

![image](https://github.com/user-attachments/assets/22874b5c-4f26-4515-905b-5bc2316009f1)

![image](https://github.com/user-attachments/assets/afb5ae39-6eaf-44d4-b482-852f586a5be2)

<br />
 
 - Wait for the changes to apply and click close

![image](https://github.com/user-attachments/assets/7ba197a1-5948-4c40-8fb8-89be8f6023c6)

<br />

<h3>4. Install PHP manager for IIS</h3>

 - From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)







From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root

Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”

Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

