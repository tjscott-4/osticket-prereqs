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
<img src="https://i.imgur.com/DJmEXEB.png" alt="Azure VM Creation Screenshot Placeholder" width="80%"/>
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
<img src="https://i.imgur.com/DJmEXEB.png" alt="IIS Installation Screenshot Placeholder" width="80%"/>
</p>

- Enabled IIS with <b>CGI</b> support via “Turn Windows features on or off”  
  - World Wide Web Services → Application Development Features → ✅ CGI  
- IIS acts as the web server to host osTicket.  

<b>Why this matters:</b> IIS is commonly used in enterprise environments; configuring it demonstrates server management fundamentals.  
**Skills demonstrated:** Windows server configuration, web hosting setup.

---

<h3>Step 3: Install PHP and Configure in IIS</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="PHP Configuration Screenshot Placeholder" width="80%"/>
</p>

- Installed:
  - PHP Manager for IIS (`PHPManagerForIIS_V1.5.0.msi`)
  - IIS Rewrite Module (`rewrite_amd64_en-US.msi`)
- Created `C:\PHP` directory and extracted `php-7.3.8-nts-Win32-VC15-x86.zip` into it.  
- Installed `VC_redist.x86.exe` to support PHP runtime.  
- Registered PHP in IIS → PHP Manager → `C:\PHP\php-cgi.exe`.  
- Restarted IIS to apply changes.  

<b>Why this matters:</b> Configuring PHP bridges IIS with osTicket’s application layer.  
**Skills demonstrated:** PHP integration, web server configuration, environment variable setup.

---

<h3>Step 4: Install MySQL Database</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="MySQL Installation Screenshot Placeholder" width="80%"/>
</p>

- Installed MySQL 5.5.62 → Typical setup → Launched Configuration Wizard  
- Set root credentials:  
  - Username: <code>root</code>  
  - Password: <code>root</code>  

<b>Why this matters:</b> osTicket stores its ticket data in MySQL; understanding databases is vital for backend troubleshooting.  
**Skills demonstrated:** Database installation, credential management, service configuration.

---

<h3>Step 5: Install osTicket and Configure IIS Site</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="osTicket Installation Screenshot Placeholder" width="80%"/>
</p>

- Extracted `osTicket-v1.15.8.zip` → copied “upload” folder into `C:\inetpub\wwwroot`  
- Renamed “upload” → “osTicket”  
- Restarted IIS → browsed to <code>http://localhost/osTicket</code>  

<b>Why this matters:</b> This connects the web server to the help desk application, making it accessible via browser.  
**Skills demonstrated:** Web directory management, application deployment.

---

<h3>Step 6: Enable Required PHP Extensions</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="PHP Extensions Screenshot Placeholder" width="80%"/>
</p>

- In IIS → PHP Manager → “Enable or disable an extension”  
- Enabled:  
  - `php_imap.dll`  
  - `php_intl.dll`  
  - `php_opcache.dll`  

<b>Why this matters:</b> These extensions enable email handling, internationalization, and performance optimization for osTicket.  
**Skills demonstrated:** Application configuration, PHP environment tuning.

---

<h3>Step 7: Configure osTicket Permissions</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="Permissions Configuration Screenshot Placeholder" width="80%"/>
</p>

- Renamed configuration file:  
  - From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`  
  - To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`  
- Disabled inheritance and added new permission:  
  - <b>Everyone → Full Control</b>  

<b>Why this matters:</b> Proper permissions prevent access errors during installation.  
**Skills demonstrated:** File system security, permission management.

---

<h3>Step 8: Create Database in HeidiSQL</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="HeidiSQL Screenshot Placeholder" width="80%"/>
</p>

- Installed HeidiSQL → connected using root credentials  
- Created a new database named <b>osTicket</b>  

<b>Why this matters:</b> A working database connection is required for osTicket to store tickets, users, and configurations.  
**Skills demonstrated:** Database administration, schema creation.

---

<h3>Step 9: Complete osTicket Setup in Browser</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="osTicket Web Setup Screenshot Placeholder" width="80%"/>
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

<h3>Step 10: Post-Installation Cleanup</h3>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="Cleanup Screenshot Placeholder" width="80%"/>
</p>

- Deleted setup directory: `C:\inetpub\wwwroot\osTicket\setup`  
- Set `ost-config.php` to read-only.  

<b>Why this matters:</b> Securing configuration files and removing setup scripts reduces security risks.  
**Skills demonstrated:** System hardening, configuration management.

---

<h2>Final Result</h2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" alt="osTicket Final Login Page Screenshot Placeholder" width="80%"/>
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
