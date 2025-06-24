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
 
   - Go to Microsoft Azure Portal > click the search bar > type virtual machines and click Virtual Machines.
    
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

