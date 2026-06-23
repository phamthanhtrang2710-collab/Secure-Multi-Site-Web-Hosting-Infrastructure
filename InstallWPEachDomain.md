# Download WordPress
    cd /tmp
    wget https://wordpress.org/latest.tar.gz
    tar -xvf latest.tar.gz

# Install for mine.com
    sudo cp -r wordpress/* /var/www/mine.com/
    sudo chown -R www-data:www-data /var/www/mine.com
# Install for minephp.com
    sudo cp -r wordpress/* /var/www/minephp.com/
    sudo chown -R www-data:www-data /var/www/minephp.com

