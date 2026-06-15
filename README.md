# Secure Multi-Site Web Hosting Infrastructure
In this project, I will focus on building a secure multi-site web hosting environment using the LAMP stack on a virtualized Linux system, deploying WordPress websites with Apache VirtualHosts, configuring HTTPS with SSL, and managing the database with appropriate access permissions.
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
      ├── site1.local
      │   ├── WordPress (Content Management System)
      │   ├── site1db
      │   └── site1user
      │
      └── site2.local
          ├── WordPress
          ├── site2db
          └── site2user

View Architecture Diagram here: 

# Project Highlights

## Multi-site Hosting

* Deploy and operate two independent WordPress websites on the same Ubuntu server.

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


