<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Welcome to the osTicket tutorial! Here, we will outline the prerequisites and installation of the open-source help desk ticketing system. We will use Azure for this so if you don't have Microsoft Azure yet, go check <a href="https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account">Azure</a> for a free account with $200 credit so you can start.<br />


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

 - To open Remote Desktop, press Windows Key or click on the start button , type Remote Desktop and click Remote Desktop Connection.

![image](https://github.com/user-attachments/assets/bb37d1ab-456a-4fea-af52-66b6a38cfecd)

<br />

- Once you open Remote Desktop Connection, you will need to fill in the IP address of your VM.

![image](https://github.com/user-attachments/assets/1675bf49-1db2-42f0-9cb9-a4c9e1aa5241)

<br />

- To obtain your VM's IP address, go back to Microsoft Azure Portal and you should see your VM listed and click.
- Alternatively, you can also click Virtual Machines / Use the search box, type virtual machine and click Virtual Machines.

![image](https://github.com/user-attachments/assets/6f3e5323-26fd-4a3e-b409-e8fea6316bea)

<br />

 - You can find your VM's IP address two ways. Either way, copy the IP address and paste it onto Remote Desktop Connection.
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
 
 - Wait for the changes to apply and click Close

![image](https://github.com/user-attachments/assets/7ba197a1-5948-4c40-8fb8-89be8f6023c6)

<br />

<h3>4. Install PHP manager for IIS</h3>

 - From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

![image](https://github.com/user-attachments/assets/74487822-9820-4da6-81c1-32812257e65c)

<br />

- Within PHP Manager setup, click Next > click I agree then Next > wait for installion to finish then click Close

![image](https://github.com/user-attachments/assets/499fe4d1-9aa8-4fb1-999c-cf2b5100861c)

<br />

<h3>5. Install Rewrite Module</h3>

 - From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

![image](https://github.com/user-attachments/assets/ec71cc91-c322-4e2b-a9b5-a14f50e25882)

<br />

 - Within the Rewrite Module setup, click I accept the terms > Install > Finish

![image](https://github.com/user-attachments/assets/98010e9b-5324-472b-ac46-f0dc2452e9ea)

![image](https://github.com/user-attachments/assets/fb843dd4-93c6-402d-ace4-3fbab4b942cf)

<br />

<h3>6. Extract PHP 7.3.8 folder into C:\PHP folder</h3>

  - Create the directory C:\PHP
 
    - To create this, go to file explorer (a folder icon on your taskbar) and click

    - Within file explorer, click This PC > click Windows (C:) drive > right click on any blank space > hover to New > click folder > name folder PHP


![image](https://github.com/user-attachments/assets/343781ea-5bc4-4947-8b0d-7d6fc5ce489a)
 
![image](https://github.com/user-attachments/assets/63759198-8e6f-48cc-b0da-8b2cb011aca6)

![image](https://github.com/user-attachments/assets/d69639b7-bc81-48d8-b7ff-14b16466dc58)

![image](https://github.com/user-attachments/assets/95d76010-ceca-4efb-be7d-fb6cdbbb119f)

<br />

  - From the “osTicket-Installation-Files” folder, extract PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
  
    - To extract, right click on the folder > click Extract All > click Browse > click This PC and Windows C: > click PHP folder then Select Folder > click Extract

![image](https://github.com/user-attachments/assets/a88edf2f-6c15-43bd-8af2-134f86778879)

![image](https://github.com/user-attachments/assets/a365492b-371e-4f4f-a74c-e4f735babe20)

![image](https://github.com/user-attachments/assets/77664163-274b-43e0-94ce-0e655fc02dd6)

![image](https://github.com/user-attachments/assets/daae7a0c-68b5-435c-b5f4-2039994559d3)

![image](https://github.com/user-attachments/assets/8c509c52-222d-4150-ab9a-6af04480d601)

<br />

<h3>7. Install Visual C ++ Redistributable </h3>

 - From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

![image](https://github.com/user-attachments/assets/0ed94742-4b4a-4fcb-aea0-79a95533e8fd)

 - Click I agree then Install > Close when it's done installing.

![image](https://github.com/user-attachments/assets/f767e277-103c-41ad-ad8f-43a48f73b627)

<br />

<h3>8. Install MySQL </h3>

 - From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

![image](https://github.com/user-attachments/assets/e450ebf7-26f7-4856-8960-5cff775d9256)

 - Click Next > I accept and next > click Typical and Install > click Finish

![image](https://github.com/user-attachments/assets/c8f8a20a-2518-4662-8668-8e403c828614)

![image](https://github.com/user-attachments/assets/744c7b58-b453-44e6-832a-37855e3e69f9)

![image](https://github.com/user-attachments/assets/a87486e4-41b9-4748-8751-4cc5327c414c)

![image](https://github.com/user-attachments/assets/0efcf9e6-bf53-41f0-beeb-d7e2331109c0)

<br />

 - Within MySQL Server Instance setup, click Next > choose Standard Configuration the Next > click Next >  type root on password for both fields and click Next > click Execute

![image](https://github.com/user-attachments/assets/9292a71e-081b-4ca0-b3ad-3dc3c9db93ed)

![image](https://github.com/user-attachments/assets/d97e92b4-909f-49a0-b4b3-3fb3b4882ba1)

![image](https://github.com/user-attachments/assets/80d1a449-9e05-46a5-9c53-ba4caed43663)

![image](https://github.com/user-attachments/assets/31832317-a378-4bcf-919a-09fe0d968bc4)

![image](https://github.com/user-attachments/assets/de2fa810-4997-4819-aa60-fc81a5c49fc5)

<br />

 - Press Finish

![image](https://github.com/user-attachments/assets/668f00f5-cf0a-4be5-b506-4a4ca62e03a1)

<br />

<h3>9. Register PHP from within IIS</h3>

 - Open Internet Information Services as an Administrator
    
    - Press windows key or click start button and type IIS and run as administrator

![image](https://github.com/user-attachments/assets/7f6e4212-c1f0-494d-a9f5-8aac10ee7f16)


 - Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

    - Look for PHP Manager and double click to open > click Register new PHP version > click three dots to browse > open PHP folder > select and open php-cgi

![image](https://github.com/user-attachments/assets/14b9c55e-bd93-4f0b-860d-b2f367649969)

![image](https://github.com/user-attachments/assets/0b06378d-09a9-4abe-978a-447694c3a579)

![image](https://github.com/user-attachments/assets/c3bf1a08-2ca6-46bf-9e91-01e5969baeaf)

![image](https://github.com/user-attachments/assets/bb1f7031-5050-4165-a704-18fec190afa0)

![image](https://github.com/user-attachments/assets/0e3aa7c0-453b-4399-8d70-b3f26a441dcb)


 - Click OK to register PHP

![image](https://github.com/user-attachments/assets/c91b33ba-c3dc-44d8-9db5-e2b57b5aff78)


 - Reload IIS (Open IIS, Stop and Start the server)

   - Click left arrow on the top left corner of PHP manager > click Stop > click Start

![image](https://github.com/user-attachments/assets/58e88c93-4ce0-490f-8dcc-b9444675e091)

![image](https://github.com/user-attachments/assets/65bc7802-cca7-45ee-998c-1686fab66b41)

![image](https://github.com/user-attachments/assets/bd83c28c-70fc-41d0-881e-0aa8726712ce)

<br />

<h3>10. Install osTicket v1.15.8</h3>

 - From the “osTicket-Installation-Files” folder, extract “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
    
    -  Go to osTicket-Installation Files > right click on osTicket-v1.15.8 zip and choose Extract All > click Extract 

![image](https://github.com/user-attachments/assets/33ef6f0b-13ad-4595-803e-a95353275cb6)

![image](https://github.com/user-attachments/assets/e89fb83e-830f-4f4a-83ad-2c55ad6661fe)

![image](https://github.com/user-attachments/assets/9ecfdfe7-0f54-4543-aba5-2f9a882832e2)

   - After extracting, right click on upload folder and click copy > go to This PC > go to Windows C: > go to inetpub > right click on wwwroot and paste

![image](https://github.com/user-attachments/assets/34f1817c-d768-4141-81e9-0ddb53a45828)

![image](https://github.com/user-attachments/assets/48b96fe8-174d-4793-8ca7-30b7fb1ab7a4)

![image](https://github.com/user-attachments/assets/d7e5d2af-7261-4de9-9f55-618bb30ac9c6)

![image](https://github.com/user-attachments/assets/6c24a624-00f5-48ef-a15e-4441fabfd8b6)

  
  - Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
     
     - right click on upload folder and choose rename > type osTicket

![image](https://github.com/user-attachments/assets/1f7866e3-cfe6-4bcb-a78f-dc6cf0cfc60b)

![image](https://github.com/user-attachments/assets/d6abf635-42dc-4e17-a9aa-cfa5bfef2b81)


 - Reload IIS (Open IIS, Stop and Start the server)

![image](https://github.com/user-attachments/assets/33be69ef-dfc4-4ea6-af4f-bc50fdf8669d)

![image](https://github.com/user-attachments/assets/2c84eeb0-eca8-4913-bbca-3e936f7dc785)


 - Go to sites -> Default -> click osTicket

![image](https://github.com/user-attachments/assets/658b7de1-44ee-4d44-8302-fb136d9069fc)

 - On the right, click “Browse *:80”

![image](https://github.com/user-attachments/assets/d301ac38-0f80-47dd-ba38-d1cc6a4d06b1)

 - That should open your browser and go to a page named "localhost/osTicket/setup
    
    * Note that some extensions are not enabled

![image](https://github.com/user-attachments/assets/ee34c01a-d86c-4fbb-9c85-617b310dab34)


 - Go back to IIS, sites -> Default -> osTicket

    - Double-click PHP Manager > Click “Enable or disable an extension”

      - Enable: php_imap.dll
      - Enable: php_intl.dll
      - Enable: php_opcache.dll
      - Refresh the osTicket site in your browser, observe the changes

![image](https://github.com/user-attachments/assets/6330cd63-4431-4362-aacb-d8324bfa1139)

![image](https://github.com/user-attachments/assets/c0391caa-792d-47c1-aa53-be044080ca69)

![image](https://github.com/user-attachments/assets/8432927a-ad89-4d5c-bcf4-89a8438bdb4d)

![image](https://github.com/user-attachments/assets/34c8539b-2d7c-498c-ac60-0fc41fb43805)

![image](https://github.com/user-attachments/assets/316d6f31-c562-48a5-976f-c526c5cf4026)

![image](https://github.com/user-attachments/assets/d2781362-32b0-4a3f-ba7d-a73c8b13019b)

![image](https://github.com/user-attachments/assets/212d19b0-4a2e-407c-8351-e3be4d7de479)

 - Rename: ost-config.php

    From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/user-attachments/assets/b5840b2c-e651-4acd-899a-6507ea2d189c)

![image](https://github.com/user-attachments/assets/ec1a10ca-a063-418b-a6fb-748f51273f59)

![image](https://github.com/user-attachments/assets/fea2f29f-de3b-43e7-a0a5-87ae6f011048)

![image](https://github.com/user-attachments/assets/df9aacf7-0d55-4e59-8861-ac7d603a0490)

  - Assign Permissions: ost-config.php

   - right click on ost-config.php and click Properties > go to Security and click Advanced

![image](https://github.com/user-attachments/assets/bc38d4d4-53d9-4ed4-a0ee-8dade2e84439)

![image](https://github.com/user-attachments/assets/e69260a8-a663-4c42-9874-bc0b7f0e90b1)

  - Disable inheritance -> Remove All 

![image](https://github.com/user-attachments/assets/22eb61ed-7383-472f-a410-0adb9e3084a8)

![image](https://github.com/user-attachments/assets/d14b5977-7ca7-4e23-aeb0-f5c93b05e639)


  - New Permissions -> Everyone -> All
      - Click Add > Select a Principal > Type everyone > click Check Names > click OK > click OK > click Apply then OK

![image](https://github.com/user-attachments/assets/cbc36418-17a1-483f-9fa5-32b1bd753e9f)

![image](https://github.com/user-attachments/assets/d52464c8-90f3-445e-94b6-520bba0313df)

![image](https://github.com/user-attachments/assets/c138b2ca-4fac-41e6-a83c-bb1f0f900a0c)

![image](https://github.com/user-attachments/assets/0eed6612-7e0c-4ce1-9647-322c7c881915)

<br />

<h3>11. Continue setting up osTicket in the browser</h3>

   - Click Continue

![image](https://github.com/user-attachments/assets/212d19b0-4a2e-407c-8351-e3be4d7de479)

<br />


  - Name Helpdesk > Name Default email (receives email from customers) > leave Database Settings for now
     
     * You can fill/name these to your preference

![image](https://github.com/user-attachments/assets/99128215-d619-4348-bfee-a1fd132979c8)

<br />

<h3>12. Install HeidiSQL</h3>

 - From the “osTicket-Installation-Files” folder, install HeidiSQL.
    
     - Double click Heidi SQL > click I accept then Next > click Next > click Next > click Next > click Install then Finish

![image](https://github.com/user-attachments/assets/47a1dc7e-aca5-4790-9ed3-b33564d53439)
   
![image](https://github.com/user-attachments/assets/33155605-136d-4fc5-b36b-a566d5a93db3)
     
![image](https://github.com/user-attachments/assets/070e860f-764a-4488-84a1-a4a0f21ce8e1)

![image](https://github.com/user-attachments/assets/f3bd628f-3dde-4063-a4d0-ca0ad9f7db44)

![image](https://github.com/user-attachments/assets/d8ec4a34-e692-4838-8147-fbd3872e1566)

![image](https://github.com/user-attachments/assets/25883a68-49da-491e-a158-b8b9a5d8fcad)

<br />

 - Within HeidiSQL:
 
   - Click New > Click Session in root folder > type root in password then click Open

![image](https://github.com/user-attachments/assets/c3e7cb9e-5da3-47e2-8392-483d8fbd6d3a)

![image](https://github.com/user-attachments/assets/09dc6dd0-9513-463f-a9a3-7fdb370f1f95)
 
 
   - Create a database called “osTicket”

     - right click on blank space > hover on Create New > Click Database

![image](https://github.com/user-attachments/assets/d142a2db-a923-4103-bb99-8e4b24c5f078)

![image](https://github.com/user-attachments/assets/c6ca57bb-acf6-4db1-a44b-f37debbf2dce)

![image](https://github.com/user-attachments/assets/8e71fc13-471c-4cf0-8cbf-4f9a5c948281)


<br />

<h3>13. Continue Setting up osTicket in the browser</h3>
 
 - Go back osTicket Setup and fill in the remaining fields (Database Settings)

    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: root
    - Click “Install Now!”
  
 ![image](https://github.com/user-attachments/assets/6eadc758-d80b-4846-b683-5799ee6b128d)

<br />

 ![image](https://github.com/user-attachments/assets/60d7b374-7ea8-4933-99f7-597cf35e59a1)

<br />

<h3>Browse to your help desk login page: http://localhost/osTicket/scp/login.php</h3>

![image](https://github.com/user-attachments/assets/8988c223-eff4-417c-b374-b7c70550c271)

<br />

<h4>End Users osTicket URL:http://localhost/osTicket/</h4>

![image](https://github.com/user-attachments/assets/8c93ad45-e52a-4d26-8ab4-50650b222432)

<br />

<h2>Next is <a href="https://github.com/angelobreyes/post-install-config">post-installation configuration.</a></h2>
