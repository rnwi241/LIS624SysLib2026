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

Password: *hint* look at the announcements portal. 

# Step 5. Setup WordPress through webpage.

Site Title: Library Systems

username: wisemarn

password: *hint* look at the announcements portal.

email: test@example.com

<html>http://34.134.91.174/wordpress/</html>

## Outcomes

WordPress assignment  completed.

 
