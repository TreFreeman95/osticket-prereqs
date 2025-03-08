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

<p><b>4.)Next we will need to enable IIS and CGI</b></p>
<p>Navigate to Control Panel --> Programs --> Programs and Features --> Turn Windows features on or off</p>
<p>
  <img src="https://i.imgur.com/ynUFdKW.png" height="30%" width="50%" alt="Control Panel "/>
  <img src="https://i.imgur.com/KZd6xRU.png" height="30%" width="50%" alt="Control Panel "/>
</p>

<p><b>Make sure all the following boxes are checked</b></p>
<p><img src="https://i.imgur.com/uxrt3Zc.png" height="30%" width="30%" alt="Control Panel "/></p>

<p><b>Check if this feature is working by going to your browser and typing in the loopback address 127.0.0.1</b></p>
<p><img src="https://i.imgur.com/sv3tsIU.png" height="60%" width="60%" alt="Control Panel "/></p>

<p><b>5.)Install PHP manager for IIS</b></p>
<p>From the osTicket-Installation-Files folder install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</p>
<img src= "https://i.imgur.com/iSRGjdB.jpeg" height= "50%" width="60%" alt= PHP manager/>

<p><b>6.) Install the Rewite Module</b></p>
<p>From the osTicket-Installation-Files folder install the Rewite Module (rewrite_amd64_en-US.msi)</p>
<img src="https://i.imgur.com/qqN3srj.png" height="50%" width="50%" alt="Rewite Module"/>

<p><b>7.)Create the PHP direcory</b></p>
<p>Navigate to the system c:drive and create a directory named "PHP</p>

<p><b>Unzip PHP files into the folder</b></p>
<p>From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</p>
<img src="https://i.imgur.com/zHXVS4o.jpeg" height="50%" width=" 50%"/>

<p><b>8.) Install VC redist Dependency</b></p>
<p>From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.</p>
<img src="https://i.imgur.com/hCEMJ6n.jpeg" height="50%" width="50%"/>

<p><b>9.)Install MySQL</b></p>
<p>From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)</p>

- Typical Setup ->
- Launch Configuration Wizard (after install) ->
- Standard Configuration ->
- Username: root
- Password: root

<img src="https://i.imgur.com/Ety7AsO.jpeg" height="50%" width="50%"/>
<img src="https://i.imgur.com/uVfYAT3.jpeg" height="50%" width="50%"/>
<img src="https://i.imgur.com/51tpP9L.jpeg" height="50%" width="50%"/>
<img src="https://i.imgur.com/SWUbZXv.jpeg" height="50%" width="50%"/>

<p><b>10.)Next we will have to register PHP within IIS</b></p>

<p>Open IIS as an administrator and click register new PHP version</p>
<img src="https://i.imgur.com/GODTj2E.png" height="50%" width="50%"/>

<p>When clicked register under PHP folder created in the C:drive (C:\PHP\php-cgi.exe)</p>
<img src="https://i.imgur.com/lc4qP0s.png" height="50%" width="50%"/>

<p>Reload IIS (Open IIS, Stop and Start the server)</p>
<img src="https://i.imgur.com/LDNGiIt.png" height="30%" width="30%" />

<h3><b>11.)Now we get to install osTicket</b></h3>

- From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” 
- Copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
  
<img src="https://i.imgur.com/PAQTIOE.jpeg" height="50%" width="50%" />

<p>Reload IIS (Open IIS, Stop and Start the server)</p>
<img src="https://i.imgur.com/LDNGiIt.png" height="30%" width="30%" />

<p>Navigate to osTicket through IIS</p>
<p>Go to sites -> Default -> osTicket. On the right, click “Browse *:80”</p>
<img src="https://i.imgur.com/OtFm4gV.png" height="50%" width="50%"/>

<p>We've launched osTicket and now need to enable required extensions for osTicket.</p>
<p>We will need to enable these extensions in IIS</p>
<img src="https://i.imgur.com/7KZsybb.png" height="50%" width="50%"/>

<p>To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Double click PHP manager -Click "Enable or disable an extension"</p>
<img src="" height="50%" width="50%"/>
<div style="display: flex; flex-direction: row;">>
    <img src=https://i.imgur.com/PAKfiT3.png" width="250" />
    <img src="images/git-hooks.webp" width="250" />
    <img src="images/python-tab.webp" width="250" />
</div>




