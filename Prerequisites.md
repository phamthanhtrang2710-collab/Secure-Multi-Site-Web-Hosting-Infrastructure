# Update the system
    sudo apt update && sudo apt upgrade -y
# Install Apache
    sudo apt install apache2 -y
Enable modules:

    sudo a2enmod  ssl 
    sudo systemctl reload apache2
# Install PHP and Extension
    sudo apt install php libapache2-mod-php php-cli php-mysql php-xml php-curl php-mbstring 
# Install MariaBD
    sudo apt install mariadb-server mariadb-client -y
    
