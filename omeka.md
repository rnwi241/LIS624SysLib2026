


## Omeka Assignment Quick Notes

# Step 1: Create new VM in Google Cloud
 
Create instance, select Ubuntu, allow html - verify

# Step 2. Update system

```sudo apt update```
```sudo apt upgrade```
```sudo apt clean```

Note: The new system may not need upgrades, but this process is used as a best practice.

# Step 3. Install software packages for final project.

```sudo apt install apache2 php libapache2-mod-php mysql-server  php-mysql php-curl php-xml php-imagick php-mbstring php-zip php-intl imagemagick unzip```

Finalize installation method:

```sudo mysql_secure_installation```

# Step 4. Modify Apache2

```sudo nano /etc/apache2/mods-enabled/dir.conf```

Rewrite file so index.php displays first.

```DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm```

Restart apache2

```sudo a2enmod rewrite```  
```sudo systemctl reload apache2```  
```sudo systemctl restart apache2```

# Step 5. Download WordPress and Omeka to VM

Go to the directory
```cd ~```

WordPress
```wget https://wordpress.org/latest.zip```

Omeka
```wget https://github.com/omeka/Omeka/releases/download/v3.2/omeka-3.2.zip```

Unzip files
```unzip latest.zip```
```unzip omeka-3.2.zip```

Rename the omeka directory

```mv omeka-3.2 omeka```

Move WordPress and Omeka to the document root.

```sudo mv wordpress /var/www/html/```
```sudo mv omeka /var/www/html/```

# Step 6. MySQL Setup

```sudo mysql -u root```

Create databases and users

```create user 'wordpress'@'localhost' identified by 'my_p4ssw0rd';```
```create user 'omeka'@'localhost' identified by 'my_p4ssw0rd';```
```create database wordpress;```
```create database omeka;```
```grant all privileges on wordpress.* to 'wordpress'@'localhost';```
```grant all privileges on omeka.* to 'omeka'@'localhost';```

Verify databases in MySQL

```show databases;```

wordpress and omeka should be listed. Then exit

```\q;```

# Step 7. Establish crendential for WordPress and Omeka

WordPress

```cd /var/www/html/wordpress
sudo cp wp-config-sample.php wp-config.php
sudo nano wp-config.php```

Omeka

```cd /var/www/html/omeka
sudo cp db.ini db.ini.backup
sudo nano db.ini```

# Step 8. Web Install of WordPress

<html>http://34.134.91.174/wordpress/</html>

Follow prompts to setup administrative credentials in WP:

Site Title: Library Systems

username: wisemarn

password: hint look at the announcements portal.

email: test@example.com

Note: The wordpress.md file in GitHub has been updated to reflect this new information. 

Create directory:

```sudo mkdir /var/www/html/wordpress/wp-content/uploads```

Change directory ownership:

```cd /var/www/html/
sudo chown -R :www-data wordpress/```

Change permissions in to allow editing:

Navigate to root directory

```cd wordpress/```

Use command line:

```sudo chmod -R 774 wp-content/```

# Step 9. Web Install of Omeka

<html>http://34.134.91.174/omeka/</html>

Follow prompts to setup administrative credentials in omeka.

# Step 10. Grant permissions in Omeka

Directory

```/etc/apache2/apache2.conf```

Add to document file:

<Directory /var/www/html/omeka>
        Options Indexes FollowSymLinks
        AllowOverride ALL
        Require all granted
</Directory>

Make sure ALL is in caps.

Restart apache2

```sudo systemctl restart apache2```

# Step 11. Troubleshoot error messages in Omeka

```sudo chown -R :www-data /var/www/html/omeka```
```sudo chmod -R 774 /var/www/html/omeka```

# User Information

DB Name: omeka

User: omeka

Password: my_p4ssw0rd

# Crendentials

Site Title: Library Systems

username: wisemarn

password: *hint* look at the announcements portal.                      

email: test@example.com

<html>http://34.134.91.174/omeka/</html>

# Reflection

This assignment needed to be turned in late because of software installation issues as well as VM space concerns.

Solutions:

-Created new VM in Google Cloud.

-Utilized new installation instructions assessed through the Canvas portal for LIS624 Systems Librarianship. 

## Outcomes

Omeka installation complete. 

Documentation successfully updated to reflect command line and installation procedures. 
