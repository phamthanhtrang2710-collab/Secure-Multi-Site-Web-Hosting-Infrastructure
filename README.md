# Secure Multi-Site Web Hosting Infrastructure
Before undertaking this project, I wondered, "How can a business host multiple websites on a single server while ensuring security, isolation, and cost-effectiveness?"

That's the main reason I started this project, by designing and deploying a secure multi-site hosting environment on an Ubuntu server using the LAMP stack (including Linux, Apache, MariaDB, and PHP). This solution hosts two independent WordPress websites, mine.com and minephp.com, via Apache VirtualHosts, with a MariaDB database and separate database users for each site.

HTTPS is enabled using SSL/TLS to secure data transmission and protect user communications. This project highlights my practical experience in Linux system administration, web hosting, database security, and real-world infrastructure deployment.

Continue exploring the sections below to learn how I designed, deployed, and secured this multi-website hosting environment.

# Project Objectives

* Fully deploy a LAMP Stack environment.

* Host multiple websites on a single Linux server.

* Configure Apache VirtualHosts to isolate each website.

* Deploy WordPress to each website.

* Apply SSL/TLS encryption to secure connections.

* Redirect all HTTP traffic to HTTPS.

* Implement database security measures according to best practices.

* Configure file and directory access permissions on Linux.

* Test and verify the functionality and availability of services.

* Document the deployment process and troubleshooting steps thoroughly.

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

# Website Configuration

| Configuration | Website 1 | Website 2 |
|---------------|-----------|-----------|
| Domain | mine.com | minephp.com |
| Platform | WordPress | WordPress |
| Document Root | /var/www/mine.com | /var/www/minephp.com |
| Database | mine | minephp |
| Database User | mineuser | minephpuser |

# Apache VirtualHost

## Http VitualHost 

<VirtualHost *:80>
    ServerName mine.com
    ServerAlias www.mine.com

    Redirect permanent / https://mine.com/

    DocumentRoot /var/www/mine.com
</VirtualHost>
