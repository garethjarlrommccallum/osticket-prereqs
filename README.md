<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>


<h1>osTicket - Prerequisites and Installation</h1>
This tutorial covers the requirements and installation process for the open-source help desk ticketing system, osTicket. osTicket is a widely used and trusted open source Help Desk ticketing system<br />

<h2>Objective</h2>
To successfully set up all prerequisites and install osTicket from scratch on a Windows 10 Virtual Machine hosted in Azure, providing a foundational help desk ticketing system.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine 
- osTicket Installation files
  ![image](https://github.com/user-attachments/assets/3dea1f52-d2df-49e4-8535-a67379360481)


<h2>Installation Steps</h2>

- Create a resource group in Microsoft Azure named osTicket. 
- Create a virtual machine within this resource group. 
- Setup the Virtual Machine, ensuring it has at least 2 vCPUs.
- Allow Azure to create Virtual Network
</p>
<br />

<p>
  
  ![image](https://github.com/user-attachments/assets/ad2d8571-e072-4853-8eb8-2d8913fcf459)

</p>

<p>
Access the VM via Remote Desktop Protocol (RDP). Once connected to the VM, enable Internet Information Services (IIS) by: 
  
Opening the Control Panel.

Click on Programs.

Select Turn Windows features on or off.

Locate and enable Internet Information Services (IIS) by:

Expanding World Wide Web Services.

Navigating to Application Development Features.

Checking CGI.

Click OK to apply changes and close the window.
</p>
<br />

<p>
  
  ![image](https://github.com/user-attachments/assets/3d3b945c-3df7-45b6-8b6f-24e0eaf8d2c6)

</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/jdy6kVT.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD Next, use the provided download link to obtain all the necessary files to install and launch osTicket.  
From the osTicket Installation folder, locate and install PHP Manager to proceed with the setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/BraQ2Sp.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the same folder, install the Rewrite Module to continue configuring the environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/3G7QEou.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BJ7pQXn.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP. Unzip the file PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and extract all its contents into the C:\PHP directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/vnapOUJ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install VC_redist.x86.exe from the osTicket Installation folder to ensure the necessary Visual C++ Redistributable components are in place.
</p>
<br />

<p>
<img src="https://i.imgur.com/6Ni4PkJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket Installation folder to set up the MySQL database server.
</p>
<br />

<p>
<img src="https://i.imgur.com/HFBKqHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS Manager as an administrator. Register PHP within IIS by configuring the necessary settings. Afterward, restart the server by selecting Restart in the IIS Manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/dUEDOI2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip and copy the upload folder to C:\inetpub\wwwroot. Then, within C:\inetpub\wwwroot, rename the upload folder to osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/ofoOo0Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Return to IIS Manager and restart the server. Enable the necessary PHP extensions by navigating to Sites -> Default -> osTicket, then double-click PHP Manager. Select "Disable or enable an extension" and enable php_intl.dll, php_opcache.dll, and php_imap.dll. Afterward, refresh the osTicket web server and verify that the Intl Extension is now enabled.
</p>
<br />

<p>
<img src="https://i.imgur.com/JEdBG6b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to ost-config.php in the same directory (C:\inetpub\wwwroot\osTicket\include).
</p>
<br />

<p>
<img src="https://i.imgur.com/vFIs9DL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign the appropriate permissions to ost-config.php by right-clicking the file and selecting Properties. In the Security tab, disable inheritance, remove all existing permissions, and grant Everyone full access.
</p>
<br />

<p>
<img src="https://i.imgur.com/HZnNtf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, proceed with the osTicket setup in your browser by clicking Continue. Assign a name to your helpdesk as desired, and select a default email address to receive customer-submitted ticket notifications. 
</p>

