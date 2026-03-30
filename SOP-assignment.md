Setup a Virtual Linux Server for Web Application Testing

**Instructor:** Felix  
**Date:** March 30, 2026  
**Type:** MarkDown  

---

## Standard Operating Procedure
**Student Name:** Armaanjot Singh
**Company name:** NSA  
**Company street address:** Winnipeg, Manitoba, Canada  
**Company or department phone number:** N/A  

**Reversion info:** Version 1.0 – Initial Release – March 2026  

---

## Approved Table

| Version | Date | Name | Designation |
|--------|------|------|-------------|
| 1.0 | March 2026 | Armaanjot Singh | Author |
| 1.1 | March 2026 | Instructor | Reviewer |

---

## Purpose

The purpose of this SOP is to provide clear instructions for setting up a Virtual Linux Server for web application testing. This ensures a consistent, secure, and properly configured environment using Ubuntu Server, Apache, MySQL, and PHP.

---

## Scope

This SOP applies to students and system administrators responsible for creating a Linux-based virtual server for web application testing using virtualization tools such as VirtualBox or VMware.

### Objectives

- Create a virtual machine  
- Install Ubuntu Server  
- Configure networking  
- Install Apache web server  
- Install MySQL database  
- Install PHP environment  
- Configure firewall  
- Verify server readiness  

---

## Accountability Matrix

| Task | Responsible Role |
|------|-----------------|
| Install virtualization software | System Administrator |
| Create virtual machine | System Administrator |
| Install Ubuntu Server | System Administrator |
| Configure networking | System Administrator |
| Install Apache | System Administrator |
| Install MySQL | Database Administrator |
| Install PHP | System Administrator |
| Configure firewall | Security Administrator |
| Test environment | Tester |

---

## Definitions

**VM:** Virtual machine created using virtualization software  
**Ubuntu Server:** Linux operating system for server use  
**Apache:** Web server software  
**MySQL:** Database management system  
**PHP:** Server-side scripting language  

---

## Procedure Steps

### Step 1: Install Virtualization Software

Install VirtualBox or VMware Workstation and ensure virtualization is enabled in BIOS.

---

### Step 2: Create Virtual Machine

Create a new virtual machine with:

- Name: WebTestServer01  
- OS: Ubuntu Server 22.04  
- RAM: 4 GB  
- CPU: 2 cores  
- Disk: 20 GB  
- Network: NAT  

Attach Ubuntu Server ISO and start VM.

---

### Step 3: Install Ubuntu Server

Install Ubuntu Server and configure:

- Username  
- Password  
- Hostname: webtestserver01  

Enable OpenSSH server and restart system.

---

### Step 4: Install Web Server Components

Run the following commands:


sudo apt update
sudo apt upgrade -y
sudo apt install apache2 -y
sudo apt install mysql-server -y
sudo mysql_secure_installation
sudo apt install php libapache2-mod-php php-mysql -y


Restart Apache:


sudo systemctl restart apache2


---

### Step 5: Configure Firewall and Test Server

Allow Apache:


sudo ufw allow Apache
sudo ufw enable


Create test file:


sudo nano /var/www/html/info.php


Add:

<?php phpinfo(); ?>

Open in browser:


http://server-ip/info.php


---

## Reversion Table

| Issue | Solution |
|------|----------|
| VM not starting | Restart virtualization software |
| Installation failed | Reinstall Ubuntu |
| Apache not working | Restart Apache |
| MySQL error | Reinstall MySQL |
| Network issue | Restart network |
| Configuration error | Restore snapshot |

---

## Approval Table

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Armaanjot Singh | Author | ______ | ______ |
| Instructor | Reviewer | ______ | ______ |

---

## Reference or Related Documents

- Ubuntu Server Documentation  
- Apache Documentation  
- MySQL Documentation  
- PHP Documentation  
- VirtualBox User Guide  
- VMware Documentation  
