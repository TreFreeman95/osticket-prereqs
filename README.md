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
<img src="https://i.imgur.com/Tj4r5V6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p><b>2.) Once you have created your virtual machine you will want to connect to it by using the public ip address the vm is setup with. You will connect using the remote desktop connection app.</b></p>
<br />

<p>
<img src="https://i.imgur.com/iTWyTzw.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

<p><b>3.)Download the osTicket-installation-files.zip and unzip it on to your remote desktop.</b></p>
<p>We will use the files in this folder to install osTicket and some of the dependencies</p>
<p>The folder should be called "osTicket-Installation-Files</p>

<img src="https://i.imgur.com/V8mUNPQ.jpeg" height="50%" width="50%" alt="folder download"/>
<br />

<p><b>4.)Next we will need to enable IIS and CGI</b></p>
<p>Navigate to Control Panel --> Programs --> Programs and Features --> Turn Windows features on or off</p>
  <img src="https://i.imgur.com/w4UPobO.png" height="60%" width="50%" alt="Control Panel "/>
  <img src="https://i.imgur.com/8HmT6G8.png" height="50%" width="50%" alt='Control Panel'/>
<p><b>Make sure all the following boxes are checked</b></p>
<p>  <img src="https://i.imgur.com/EXbeltI.png" height="50%" width="30%" alt="Control Panel "/></p>

<p><b>Check if this feature is working by going to your browser and typing in the loopback address 127.0.0.1</b></p>
<p><img src="https://i.imgur.com/Wi7z0Fk.png" height="60%" width="60%" alt="Control Panel "/></p>

<p><b>5.)Install PHP manager for IIS</b></p>
<p>From the osTicket-Installation-Files folder install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</p>
<img src= "https://i.imgur.com/IsTbhCm.png" height= "50%" width="60%" alt= PHP manager/>

<p><b>6.) Install the Rewite Module</b></p>
<p>From the osTicket-Installation-Files folder install the Rewite Module (rewrite_amd64_en-US.msi)</p>
<img src="https://i.imgur.com/DtnRxcf.png" height="50%" width="50%" alt="Rewite Module"/>

<p><b>7.)Create the PHP direcory</b></p>
<p>Navigate to the system c:drive and create a directory named "PHP</p>

<p><b>Unzip PHP files into the folder</b></p>
<p>From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</p>
<img src="https://i.imgur.com/RCzj7nY.jpeg" height="50%" width=" 50%"/>

<p><b>8.) Install VC redist Dependency</b></p>
<p>From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.</p>
<img src="https://i.imgur.com/F3Ok7El.jpeg" height="50%" width="50%"/>

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
<img src="https://i.imgur.com/F3Ok7El.jpeg" height="50%" width="50%"/>

<p>When clicked register under PHP folder created in the C:drive (C:\PHP\php-cgi.exe)</p>
<img src="https://i.imgur.com/cbIoWdn.png" height="50%" width="50%"/>
<img src="https://i.imgur.com/XmPFZOK.jpeg" height="50%" width="50%"/>


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
<img src="https://i.imgur.com/NubMK2w.jpeg" height="60%" width="40%"/>
<img src="https://i.imgur.com/9kHCPCG.jpeg" height="60%" width="40%"/>


<p>We've launched osTicket and now need to enable required extensions for osTicket.</p>
<p>We will need to enable these extensions in IIS</p>
<img src="https://i.imgur.com/7KZsybb.png" height="50%" width="50%"/>
</br>

<p>To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Double click PHP manager -Click "Enable or disable an extension"</p>
<div style="display: flex; flex-direction: row; flex-wrap:wrap;">
    <img src="https://i.imgur.com/PAKfiT3.png" width="60%" />
    <img src="https://i.imgur.com/1yr0VCh.png" width="70%" height="50%"/>
    <p>We will want to enable three extensions from here.</p>
      <ol>
        <li>php_imap.dll</li>
        <li>php_intl.dll</li>
        <li>php_opcache.dll</li>
      </ol>
      <img src="https://i.imgur.com/UKbsV2z.png" width="70%" />
</div>
</br>

<p>Refresh the osTicket site in your browser, observe the changes</p>
<img src="https://i.imgur.com/GgWeGFe.jpeg" width="70%" />

<p>Next we will have to navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to ost-config.php in the same directory (C:\inetpub\wwwroot\osTicket\include).</p>
<img src="https://i.imgur.com/VhPOY0e.png" width="70%" />

<p>Assign Permissions: ost-config.php</p>
<p>Now that we have renamed the files, right click on the file and go to properties. From there click security, click on advance, and disable the inheritance. We will select Remove all inherited permissions from this object.</p>

  <img src="https://i.imgur.com/zsQjlr8.png"/>

  <p>New Permissions -> Everyone -> All</p>
  <img src="https://i.imgur.com/KAfFfR5.png"/>

<h2>Intial osTicket Install</h2>
<h3>Continue Setting up osTicket in the browser</h3>
<ol>
  <li>Name Helpdesk</li>
  <li>Default Email(This email will receive emails from customers)</li>
</ol>

<p>For Admin User I made sure the email was different from the default system email</p>
  <img src="https://i.imgur.com/ApTqHn4.png"/>


<h3>Install HeidiSQL</h3>
<p>From the “osTicket-Installation-Files” folder, install HeidiSQL.</p>
<img src="https://i.imgur.com/Lct6xno.png"/>


<ol>
  <li>Open Heidi SQL</li>
  <li>Create a new session</li>
  <li>Make sure to set the  to User:root Password:root</li>
  <li>Connect to the session</li>
</ol>

<img src="https://i.imgur.com/UiqZzWQ.png"/>

<p>When done create a new database by right clicking unnamed and name it osTicket</p>

<img src="https://i.imgur.com/rRDH2ui.png"/>

<h3>Continue osTicket install</h3>

<p>Let's continue setting up osTicket in the browser</p>

<p>Let's finish setting up the database settings</p>
<ul>
  <li>MySQL Database: osTicket</li>
  <li>MySQL Username: root</li>
  <li>MySQL Password: root</li>
  <li>Click "Install Now"</li>
  
</ul>
<img src="https://i.imgur.com/HvXdE5X.png"/>

<h2>Congratulations osTicket is installed</h2>
<img src="https://i.imgur.com/JUmoulh.png" />

<h3>Now login in adminuser: <a href='http://localhost/osTicket/scp/login.php'>http://localhost/osTicket/scp/login.php</a></h3>
<img src="https://i.imgur.com/FKaKkS2.png"/>
