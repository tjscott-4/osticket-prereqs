# osticket-prereqs
<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo" width="300"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

<h2>Project Summary</h2>
<p>
This project demonstrates the deployment and configuration of the open-source <b>osTicket Help Desk Ticketing System</b> within a <b>Windows 10 Virtual Machine</b> hosted in <b>Microsoft Azure</b>.  
It covers setting up <b>IIS</b> as a web server, installing <b>PHP</b> and <b>MySQL</b>, configuring file permissions, and finalizing the osTicket installation.  
This project showcases key <b>IT support, system administration, and troubleshooting</b> skills used in real-world technical environments.
</p>

---

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- PHP 7.3.8
- MySQL 5.5
- HeidiSQL

<h2>Operating Systems Used</h2>

- Windows 10 (21H2)

---

<h2>List of Prerequisites</h2>

- Azure account to host the virtual machine  
- Windows 10 Virtual Machine (4 vCPUs, 8 GB RAM recommended)  
- Remote Desktop access to the VM  
- IIS (Internet Information Services) installed with CGI enabled  
- PHP Manager and Rewrite Module for IIS  
- PHP 7.3.8 files extracted to `C:\PHP`  
- Visual C++ Redistributable (VC_redist.x86.exe)  
- MySQL Server 5.5 with root credentials  
- osTicket installation files  
- HeidiSQL for database management  

---

<h2>Installation Steps</h2>

---

<h3>Step 1: Create and Access Azure Virtual Machine</h3>
<p>
<img width="547" height="443" alt="image" src="https://github.com/user-attachments/assets/84a79156-8cb2-460f-babc-764c1b5ca819" />
</p>

- Created a Windows 10 VM in Azure named <b>osticket-vm</b>  
- Specifications: 4 vCPUs  
- Username: <code>labuser</code>  
- Password: <code>osTicketPassword1!</code>  
- Connected to the VM using <b>Remote Desktop (RDP)</b>  

<b>Why this matters:</b> Cloud-hosted environments mimic real-world IT infrastructure setups and demonstrate understanding of virtualization.  
**Skills demonstrated:** Azure VM provisioning, RDP connectivity, basic system access management.

---

<h3>Step 2: Install and Configure IIS (Internet Information Services)</h3>
<p>
<img width="1117" height="635" alt="image" src="https://github.com/user-attachments/assets/b604a947-0d75-4226-b7ef-d9a0df11400f" />


1.Navigate to: Control Panel → Programs → Turn Windows features on or off

2.Check Internet Information Services (IIS)

3.Expand World Wide Web Services → Application Development Features

4.Enable CGI → Click OK, then Close once installation completes

💡 Explanation:
Enabled IIS with CGI support to host the osTicket web application.
IIS acts as the web server, and CGI allows dynamic processing for PHP-based applications.

📘 Why this matters:
IIS is a standard web hosting solution used in enterprise environments. Configuring it demonstrates foundational skills in Windows server management and web service deployment.

🧩 Skills demonstrated:

Windows Server configuration

Web hosting setup using IIS

Understanding of CGI and PHP integration

---

<h3>Step 3: Install PHP and Configure in IIS</h3>
<p>
<img width="494" height="408" alt="image" src="https://github.com/user-attachments/assets/c0f09e5f-3ef7-4478-97d9-4e1422427e9e" />
<img width="489" height="382" alt="image" src="https://github.com/user-attachments/assets/386a028e-3301-4a08-813e-195834442aaf" />


1.Installed required components:

2.PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

3.IIS Rewrite Module (rewrite_amd64_en-US.msi)

4.Created a directory: C:\PHP

5.Extracted php-7.3.8-nts-Win32-VC15-x86.zip into the PHP directory

6.Installed VC_redist.x86.exe to enable PHP runtime support

7.Opened IIS Manager → PHP Manager → Register new PHP version and selected C:\PHP\php-cgi.exe

8.Restarted IIS to apply all configuration changes

💡 Explanation:
Configured PHP to work with IIS by adding the necessary runtime and modules. This step ensures IIS can process PHP scripts — essential for osTicket’s web-based functionality.

📘 Why this matters:
PHP serves as the application layer for osTicket, enabling dynamic content rendering and ticket management. Connecting it properly within IIS demonstrates understanding of web server–application integration.

🧩 Skills demonstrated:

PHP runtime setup and integration

Web server configuration

Environment and dependency management

---

<h3>Step 4: Install MySQL Database</h3>
<p>
<img width="502" height="376" alt="image" src="https://github.com/user-attachments/assets/46ee902e-516a-4918-8e7d-d1d56e59d15b" />
</p>

1.Installed MySQL 5.5.62 using the Typical setup option

2.Launched the MySQL Configuration Wizard after installation

3.Set root credentials:

  -Username: root

  -Password: root

💡 Explanation:
Installed and configured MySQL to serve as the backend database for osTicket. MySQL stores all ticket data, user information, and configuration settings.

📘 Why this matters:
Understanding database setup and credential management is essential for troubleshooting application connectivity issues and maintaining secure access to stored data.

🧩 Skills demonstrated:

Database installation and configuration

Credential and access management

Backend service setup for web applications
---

<h3>Step 5: Install osTicket and Configure IIS Site</h3>
<p>
<img width="1344" height="452" alt="image" src="https://github.com/user-attachments/assets/3d6ecf59-2b90-43cb-98af-50ed04402ebf" />
</p>

1.Extracted osTicket-v1.15.8.zip

2.Copied the “upload” folder into C:\inetpub\wwwroot

3.Renamed the folder from “upload” to “osTicket”

4.Restarted IIS

5.Opened a browser and navigated to http://localhost/osTicket
 to verify the setup

💡 Explanation:
Deployed the osTicket web application by placing its files into the IIS web root directory. Restarting IIS and testing the URL confirmed that the application was accessible through the local web server.

📘 Why this matters:
This step connects the web server to the help desk application, enabling browser-based access for users. It demonstrates practical knowledge of web directory management and application deployment.

🧩 Skills demonstrated:

Web directory and file management

Application deployment within IIS

Basic web server testing and validation

---

<h3>Step 6: Enable Required PHP Extensions</h3>
<p>
<img width="813" height="454" alt="image" src="https://github.com/user-attachments/assets/900b39ca-43b7-4262-9815-27df83399085" />
<img width="424" height="146" alt="image" src="https://github.com/user-attachments/assets/e6bfec5f-b067-4547-adf2-82511218c64c" />
<img width="595" height="402" alt="image" src="https://github.com/user-attachments/assets/0f595401-1912-4f66-a241-11883b4884ee" />
  

</p>

1.Open IIS Manager → PHP Manager → Enable or disable an extension

2.Enabled the following PHP extensions:

  -php_imap.dll

  -php_intl.dll

  -php_opcache.dll

💡 Explanation:
These extensions provide additional functionality for osTicket:

php_imap.dll → enables email handling

php_intl.dll → supports internationalization

php_opcache.dll → improves PHP performance by caching scripts

📘 Why this matters:
Ensuring the correct PHP extensions are enabled is critical for application features and performance. It demonstrates an understanding of configuring a PHP environment for production-ready applications.

🧩 Skills demonstrated:

PHP application configuration

Environment tuning and optimization

Understanding of feature-specific extensions

---

<h3>Step 7: Configure osTicket Permissions</h3>
<p>
<img width="1128" height="489" alt="image" src="https://github.com/user-attachments/assets/d69ddcc7-9676-4653-a588-4f19a0266c4a" />
<img width="1123" height="537" alt="image" src="https://github.com/user-attachments/assets/a54db0d1-dbeb-4031-82ba-355631b5f331" />


1.Renamed the configuration file:

  -From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

  -To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

2.Disabled inheritance and set new permissions:

  -Everyone → Full Control

💡 Explanation:
Renaming the sample configuration file and setting proper permissions ensures osTicket can read/write configuration data during installation without encountering access errors.

📘 Why this matters:
Demonstrates knowledge of file system security and permission management, which are critical for preventing installation issues and ensuring application functionality.

🧩 Skills demonstrated:

File system security

Permission management

Application setup and troubleshooting

---

<h3>Step 8: Create Database in HeidiSQL</h3>
<p>
<img width="697" height="565" alt="image" src="https://github.com/user-attachments/assets/23056938-6a3d-4e36-84c3-377bb27df675" />
  <img width="1087" height="656" alt="image" src="https://github.com/user-attachments/assets/15fe4c9a-4d6f-4341-9ea5-b7884a74609b" />

</p>

1.Installed HeidiSQL

2.Connected to MySQL using root credentials

3.Created a new database named osTicket

💡 Explanation:
Used HeidiSQL to create a dedicated database for osTicket, which will store all tickets, user accounts, and configuration settings.

📘 Why this matters:
A properly configured database connection is essential for osTicket to function. This step demonstrates the ability to manage databases and create schemas for applications.

🧩 Skills demonstrated:

Database administration

Schema creation

Connecting and managing MySQL databases using GUI tools

---

<h3>Step 9: Complete osTicket Setup in Browser</h3>
<p>
<img width="1523" height="911" alt="image" src="https://github.com/user-attachments/assets/b61ad7ac-c4c2-40f3-9f73-d8a15ee70ce7" />
</p>

- Continued web setup in browser:  
  - Helpdesk name and admin email  
  - MySQL Database: <code>osTicket</code>  
  - Username: <code>root</code>  
  - Password: <code>root</code>  
- Clicked “Install Now!”  

Access URLs:  
- Admin Panel: <code>http://localhost/osTicket/scp/login.php</code>  
- End User Portal: <code>http://localhost/osTicket/</code>  

<b>Why this matters:</b> Demonstrates ability to perform end-to-end software deployment.  
**Skills demonstrated:** Web configuration, database connectivity, service setup.

---

---

<h2>Final Result</h2>
<p>
<img width="1038" height="508" alt="image" src="https://github.com/user-attachments/assets/b6b82c8f-ce63-476b-9bc3-41113cc877f9" />
</p>

✅ osTicket successfully installed and running on Windows 10 Azure VM  
✅ IIS, PHP, and MySQL properly configured  
✅ Demonstrated end-to-end deployment and IT troubleshooting workflow  

---

<h2>Key Skills Demonstrated</h2>

- Virtual Machine Deployment (Azure)  
- Web Server Configuration (IIS)  
- Database Management (MySQL, HeidiSQL)  
- Application Setup (PHP, osTicket)  
- File System Security and Permissions  
- Troubleshooting and Configuration Management  
- IT Support and Systems Administration Fundamentals
