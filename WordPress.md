# Assignment 11: WordPress Installation

## Overview

Install WordPress software on virtual machine in preparation for Systems Librarianship finals project. 

# Step 1. Confirm System Requirements


```php --version```

Php 8.36

```mysql --version```

8.0.45

Unbuntu 24.04.4 LTS

# Step 2. Update system

```sudo apt update ; sudo apt upgrade -y ; sudo apt autoremove -y ; sudo apt clean```

# Step 3. Install WordPress software

From the root directory ```cd /var/www/html```

```sudo wget https://wordpress.org/latest.zip```

```sudo unzip latest.zip```

Note this command may return: 'command not found'

Run ```sudo apt install unzip```

Rerun ```sudo unzip latest.zip```

Tips:

```ls -lh```

Command used to display root data.

# Step 4. Database and User Information

MySQL root login command:

```sudo mysql -u root```

DB Name: wordpress

User: wordpress

Password: *hint* you'll be excited to earn this in 2026. 

# Step 5. Setup WordPress through webpage.

Site Title: Sir Henry Winston Main Library

username: wisemarn

password: *hint* you'll be excited to earn this in 2026.

email: personal gmail

<html>http://34.61.47.135/wordpress/index.php/2026/04/24/welcome-to-the-sir-henry-winston-main-library/</html>

## Outcomes

WordPress assignment completed.

 
