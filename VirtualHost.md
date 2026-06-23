Open and edit the Apache VirtualHost configuration file for mine.com:

    sudo vim /etc/apache2/sites-available/mine.com.conf

Insert:

<img width="322" height="263" alt="12-mine com-config" src="https://github.com/user-attachments/assets/0aa5fa9d-33c1-4f99-91ca-3ec12aa5a69e" />

Likewise, configure minephp.com

<img width="368" height="147" alt="13-minephp com-conf" src="https://github.com/user-attachments/assets/b0b01e88-16ed-432d-8896-6eec515f00c2" />

Then, enable them

    sudo a2ensite mine.com.conf
    sudo a2ensite minephp.com.conf
    sudo systemctl reload apache2
