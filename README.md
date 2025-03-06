# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Implementing a Help Desk Ticketing System (osTicket) using Azure Virtual Machines</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine  
- Internet Information Services (IIS)
- PHP Manager
- Rewite Module 
- VC Redist
- MySQL
- osTicket-v1.15.8
- Link to the fiile downloads:<br>
  https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

<h2>Installation Steps</h2>

<p><b>1.) The first step we have to take is create a virtual machine using Microsoft Azure</b><p>
<p>Create the Azure vm with the following requirements below</p>

- Windows 10, 4 vCPUs
- Name: osticket-vm
- Username: labuser
- Password: osTicketPassword1!
<br />

<p>
<img src="https://i.imgur.com/MrTgYFf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p><b>2.) Once you have created your virtual machine you will want to connect to it by using the public ip address the vm is setup with. You will connect using the remote desktop connection app.</b></p>
<br />

<p>
<img src="https://i.imgur.com/fjj0PQW.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

<p><b>3.)Download the osTicket-installation-files.zip and unzip it on to your remote desktop.</b></p>
<p>We will use the files in this folder to install osTicket and some of the dependencies</p>
<p>The folder should be called "osTicket-Installation-Files</p>

<img src="https://i.imgur.com/ITlDslB.jpeg" height="50%" width="50%" alt="folder download"/>
<br />

<p><b>4.Next we will need to enable IIS and CGI</b></p>
<p>Navigate to Control Panel --> Programs --> Programs and Features --> Turn Windows features on or off</p>
<p>
  <img src="https://i.imgur.com/ynUFdKW.png" height="30%" width="50%" alt="Control Panel "/>
  <img src="https://i.imgur.com/KZd6xRU.png" height="30%" width="50%" alt="Control Panel "/>
</p>

<p><b>Make sure all the boxes are checked</b></p>
<p><img src="https://i.imgur.com/uxrt3Zc.png" height="30%" width="30%" alt="Control Panel "/></p>




