# osTicket Help Desk Deployment and Troubleshooting Lab

## Project Summary

This project documents the deployment, configuration, troubleshooting, and use of an osTicket help desk environment hosted on a Microsoft Azure virtual machine.

The purpose of the lab was to gain hands-on experience with technologies commonly used in IT support and system administration. I configured a Windows virtual machine, installed and configured IIS, PHP, MySQL, HeidiSQL, and osTicket, and then demonstrated a complete help desk ticket lifecycle from ticket creation through resolution.

During the implementation, I encountered several configuration issues including HTTP/HTTPS connection problems, HTTP 404 errors, missing web page styling, PHP configuration issues, file permission problems, and osTicket configuration/database issues.

Rather than only documenting the successful installation, this project also explains how I identified each problem, what clues helped narrow down the cause, why the issue occurred, and how I verified that the solution worked.

## Environments and Technologies Used

* Microsoft Azure
* Azure Virtual Machines
* Windows 10
* Internet Information Services (IIS)
* CGI / FastCGI
* PHP 7.3.8
* MySQL 5.5
* HeidiSQL
* osTicket v1.15.8
* Remote Desktop Protocol (RDP)

### Languages / Scripting

No programming or scripting language was required for the primary implementation of this project.
## Project Architecture

The lab environment was built inside Microsoft Azure using a Windows 10 virtual machine.

The basic flow of the environment was:

**User Browser → IIS Web Server → PHP → osTicket → MySQL Database**

* **Microsoft Azure** hosted the virtual machine.
* **Windows 10** provided the operating system for the help desk server.
* **IIS** hosted the osTicket website.
* **PHP** allowed IIS to process the osTicket application.
* **MySQL** stored osTicket users, tickets, configuration, and other application data.
* **HeidiSQL** was used to view and manage the MySQL database.
* **osTicket** provided the customer-facing support portal and staff ticket management system.

## Implementation Overview

### 1. Azure Virtual Machine

I created a Windows 10 virtual machine in Microsoft Azure to host the help desk environment.

The virtual machine served as the main system where IIS, PHP, MySQL, HeidiSQL, and osTicket were installed and configured.

**Skills practiced:**

* Azure Virtual Machine deployment
* Remote Desktop connectivity
* Windows administration
* Cloud resource management

### 2. IIS Web Server Configuration

Internet Information Services (IIS) was enabled on the Windows virtual machine with CGI support.

CGI/FastCGI was required so IIS could communicate with PHP and process the PHP files used by osTicket.

### 3. PHP Configuration

PHP 7.3.8 was installed in:

`C:\PHP`

PHP was then registered with IIS using:

`C:\PHP\php-cgi.exe`

Additional PHP extensions required or recommended by osTicket were enabled, including:

* `php_imap.dll`
* `php_intl.dll`
* `php_opcache.dll`

### 4. osTicket Deployment

The osTicket application files were copied into the IIS web root.

The final application path was:

`C:\inetpub\wwwroot\osTicket`

The folder name was kept exactly as **osTicket** with no spaces so that IIS could correctly locate the application.

### 5. MySQL Database

MySQL was installed and configured as the database server for osTicket.

Using HeidiSQL, I verified the osTicket database and its tables.

The database stored the help desk configuration, users, tickets, ticket history, and other application data.
## Troubleshooting and Lessons Learned

## Ticket Lifecycle Demonstration

## Skills Demonstrated

## Project Conclusion
