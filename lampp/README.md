# How to install LAMPP
## on Arch GNU/Linux Distribution
### Install apache
```sh
# Update the package manager
$ sudo pacman -Syu
# Install apache
$ sudo pacman -S apache
# Edit the configuration file
$ sudo nano /etc/httpd/conf/httpd.conf
# Comment out the unique_id_module: 
 LoadModule unique_id_module modules/mod_unique_id.so
# You can change the directory of your apache path
 DocumentRoot "/var/www"
 <Directory "/var/www">
# Restart apache
$ sudo systemctl restart httpd
# Add your hostname 127.0.0.1
$ sudo nano /etc/hosts
# Write in the file
127.0.0.1       localhost.localdomain   localhost
# Create an example index
$ sudo nano /srv/http/index.html
 <html>
  <title>Welcome</title>
  <body>
   <h2>Hello, Welcome to Arch</h2>
  </body>
 </html>
```

## Install MariaDB
```sh
# Install MariaDB
$ sudo pacman -S mariadb
# Running MariaDB
$ sudo systemctl start mysqld
# Run the mysql set up script
$ sudo mysql_secure_installation

## Install PHP
```sh
# Install PHP
$ sudo pacman -S php php-apache
# Add PHP to the apache configuration
$ sudo  nano /etc/httpd/conf/httpd.conf
# Paste this text
 # Use for PHP 5.x:
 LoadModule php5_module       modules/libphp5.so
 AddHandler php5-script php
 Include conf/extra/php5_module.conf
```

## See your PHP config
```sh
# Create a blank page
$ sudo nano /var/www/info.php
# Add the folloging line to the file
  <?php
    phpinfo();
  ?>
# Restart apache
$ sudo systemctl restart httpd
```
