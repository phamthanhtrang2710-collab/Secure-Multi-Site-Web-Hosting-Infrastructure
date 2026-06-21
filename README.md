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
Create a virtualHost configuaration file for website 1 named mine.com.conf:

      sudo vim /etc/apache2/sites-available/mine.com.conf

## Http VitualHost Website 1
    
    <VirtualHost *:80>
    ServerName mine.com
    ServerAlias www.mine.com
    Redirect permanent / https://mine.com/
    DocumentRoot /var/www/mine.com
    </VirtualHost>

## Https VirtualHost Website 1
      
    <VirtualHost *:443>
    ServerName mine.com
    ServerAlias www.mine.com
    DocumentRoot /var/www/mine.com

    SSLEngine on
    SSLCertificateFile /etc/ssl/certs/ssl-cert-snakeoil.pem
    SSLCertificateKeyFile /etc/ssl/private/ssl-cert-snakeoil.key
    </VirtualHost>

## Http and Https Website 2
Likewise, create VirtualHost file for minephp.com

    <VirtualHost *:80>
    ServerName minephp.com
    ServerAlias www.minephp.com
    Redirect permanent / https://minephp.com/
    DocumentRoot /var/www/minephp.com

    ErrorLog ${APACHE_LOG_DIR}/minephp-error.log
    CustomLog ${APACHE_LOG_DIR}/minephp-access.log combined
    </VirtualHost>
    
    <VirtualHost *:443>
    ServerName minephp.com
    ServerAlias www.minephp.com
    DocumentRoot /var/www/minephp.com

    SSLEngine on
    SSLCertificateFile /etc/ssl/certs/ssl-cert-snakeoil.pem
    SSLCertificateKeyFile /etc/ssl/private/ssl-cert-snakeoil.key

    ErrorLog ${APACHE_LOG_DIR}/minephp-ssl-error.log
    CustomLog ${APACHE_LOG_DIR}/minephp-ssl-access.log combined
    </VirtualHost>

# Database Security Design

To minimize security risks, ensure isolation between hosted websites, enhance administrative control, and protect server-side data, the database architecture for both websites should be implemented according to the following security principles:

      - One website - one database, one website - one database user
      - Appplications don't use MariaDB root account
      - Necessary database access should be follow Principle of Least Privilege
    
DB and user for mine.com

      CREATE DATABASE mine;
      
      CREATE USER 'mineuser'@'localhost' IDENTIFIED BY 'StrongPassword1!';
      
      GRANT ALL PRIVILEGES ON mine.* TO 'mineuser'@'localhost';
      
      FLUSH PRIVILEGES;

Db and user for minephp.com

      CREATE DATABASE minephp;
      
      CREATE USER 'minephpuser'@'localhost' IDENTIFIED BY 'StrongPassword2!';
      
      GRANT ALL PRIVILEGES ON minephp.* TO 'minephpuser'@'localhost';
      
      FLUSH PRIVILEGES;



