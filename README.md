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
