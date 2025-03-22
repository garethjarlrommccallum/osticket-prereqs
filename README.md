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
  
-  Opening the Control Panel.

-  Click on Programs.

-  Select Turn Windows features on or off.

-  Locate and enable Internet Information Services (IIS) by:

   -  Expanding World Wide Web Services.

   -  Navigating to Application Development Features.

   -  Checking CGI.

-  Click OK to apply changes and close the window.
</p>
<br />

<p>

  
  <h2>Install Prerequisite Programs</h2>

  ![image](https://github.com/user-attachments/assets/b6631374-243b-4547-b015-0e6613eead23)


1. Install PHP Manager
2. Install Rewrite
3. Install VC Redist
4. Install PHP:
   - Create the directory C:\PHP
   - Extract PHP files into C:\PHP directory
   - Register PHP from within IIS
   - Reload IIS (Open IIS, Stop and Start the server)

9. Install mySQL:
   - Typical Setup
   - Launch Configuration
   - Standard Configuration
   - Secret Password

10. Install HeidiSQL
    - Open HeidiSQL
    - Create a new session, root/secret password
    - Connect to session
    - Create a database called "osTicket"
   
11. Install osTicket and configure it as a website running on this web server
    - Install osTicket
    - Download osTicket
    - Extract and copy "upload" folder to C:\inetpub\wwwroot
    - Reload IIS (Open IIS, Stop and Start the server)
    - Confirm osTicket is running through the web server
      - Got to Sites -> Default -> osTicket-> "Browse *80"

12. Enable Features and assign permissions
    - Enable Extensions in PHP Manager:
       - Enable: php_imap.dll
       - Enable: php_intl.dll
       - Enable: php_opcache.dll
    - Rename ost-config.php:
       - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
       - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
    - Assign Permissions: ost-config.php
       - Disable inheritance -> Remove All
       - New Permissions -> Everyone -> All
      
13. Complete Installation by registering email and mySQL database
    - Continue setting up osTicket in the browser
    - Name Helpdesk
    - Default email (receives email from customers
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: (secret password)
    - Click "Install Now"
   
14. Confirm osTicket can be reached by users on LocalHost
    - Test link for agents and end-users:
       - Agents URL: http://localhost/osTicket/scp/login.php
       - End Users URL: http://localhost/osTicket/
      
15. Clean up files that pose a security risk
    - Delete: C:\inetpub\wwwroot\osTicket\setup
    - Set Permissions to "Read" only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  
     
