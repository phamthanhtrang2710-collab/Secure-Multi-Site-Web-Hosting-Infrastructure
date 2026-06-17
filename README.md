# Secure Multi-Site Web Hosting Infrastructure
In this project, I will build a secure multi-website hosting system on an Ubuntu server. The system uses Apache VirtualHosts to deploy and operate two independent WordPress websites, mine.com and minephp.com, each configured with a MariaDB database and a separate database account to ensure security and efficient management. Besides, SSL/TLS will be implemented to enable HTTPS, encrypting data transmitted between users and the server, thus enhancing system security.
# Architecture
WebServer:
      
      Ubuntu Server 24.04 LTS (Operating System)
      │
      ├── Apache Web Server (Apache2 - Webserver)
      │
      ├── PHP (Backend)
      │
      ├── MariaDB (Database)
      │
      ├── SSL/TLS (Security)
      │
      ├── mine.com
      │   ├── WordPress (Content Management System)
      │   ├── minedb
      │   └── mineuser
      │
      └── minephp.com
          ├── WordPress
          ├── minephpdb
          └── minephpuser

View Architecture Diagram: <img width="1536" height="1024" alt="Secure-multi-site-web-hosting-architecture" src="https://github.com/user-attachments/assets/718e8519-b0c1-41c1-8c54-b8dde4e9af13" />


# Project Highlights

## Multi-site Hosting

* Deploy and operate two WordPress websites on the same Ubuntu server.

* Configure Apache VirtualHosts to separate the configuration of each website, ensuring independence and ease of management.

## LAMP Stack Deployment

Install and fully administer the components of the LAMP model, including:

* Linux

* Apache

* MariaDB

* PHP

## HTTPs Implementation

* Enable SSL/TLS encryption to secure the connection between users and the server.

* Configure HTTPS VirtualHosts for each website.

* Set up automatic redirection from HTTP to HTTPS to ensure all access uses a secure connection.

## Database Security

* Create a separate database for each website.

* Create dedicated database user accounts for each website.

* Grant only necessary access permissions according to the principle of least privilege.

## Linux Administration

* Manage system services using systemctl.

* Configure file and directory ownership and appropriate access permissions.

* Install and maintain necessary software packages to support server operation.

## Security Hardening

* Implement strict file access permissions to restrict unauthorized access.

* Disable directory indexing on the web server.

* Configure Uncomplicated Firewall (UFW) rules to control network traffic to and from the system.

## Troubleshooting

Diagnose and resolve issues related to:

* Apache configuration.

* WordPress deployment.

* Database connection errors.

* Issues related to SSL/TLS configuration.

# Security Principle Applied

* Each website uses its own database and database user account.

* The root account is not used for applications to minimize security risks.

* Database access is granted according to the Principle of Least Privilege, meaning each account is only granted the necessary permissions to perform its function.

# SSL/TLS Configuration

HTTPS has been implemented using SSL certificates.

Security controls include:

* Data encryption using SSL/TLS to protect information transmitted between the server and users.

* Configuring a separate HTTPS VirtualHost for each website.

* Setting up automatic redirection from HTTP to HTTPS to ensure all connections are securely encrypted.

