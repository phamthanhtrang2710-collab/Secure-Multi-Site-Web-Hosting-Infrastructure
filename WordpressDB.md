# Enter Mariadb
    sudo mysql
# Create Database and User for mine.com
    CREATE DATABASE mine;
    CREATE USER 'mineuser'@'localhost' IDENTIFIED BY 'StrongPassword1!';
    GRANT ALL PRIVILEGES ON mine.* TO 'mineuser'@'localhost';
    FLUSH PRIVILEGES;

# Create Database and User for minephp.com
    CREATE DATABASE minephp;
    CREATE USER 'minephpuser'@'localhost' IDENTIFIED BY 'StrongPassword2!';
    GRANT ALL PRIVILEGES ON minephp.* TO 'minephpuser'@'localhost';
    FLUSH PRIVILEGES;
    EXIT;
