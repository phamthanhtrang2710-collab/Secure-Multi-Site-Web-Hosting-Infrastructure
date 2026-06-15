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

#
