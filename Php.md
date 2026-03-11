# 2026-08-03 Installing Apache and PHP 

## Overview

This document records my process for installing Apache and PHP on my Ubuntu VM hosted on Google Cloud.  
The goal was to verify that Apache was running and that PHP was correctly configured using a browser/OS detection script.
The documentation procedures have been updated. This module is a reflection of those changes. 

## Note

Adding files to the Git repository on my VM steps:


Pushing files to the Git repository on my VM steps:
 
## Environment

- VM Provider: Google Cloud
- OS: Ubuntu 22.04 LTS
- Web Server: Apache 2.4.52
- PHP Version: 8.1
- Browser Used for Testing: Firefox (Linux)

## Step 1. Update Package Lists

``` 
sudo apt update
```

## Step 2. Install Apache
sudo apt install apache2
Check status of install using:
systemctl status apache2
Output indicated: Active: active (running)

## Step 3. Confirm Apache in Browser
http://10.128.0.2/
I saw the default Apache2 Ubuntu page, confirming that the server was accessible.

## Step 4. Install PHP
sudo apt install php libapache2-mod-php
Installation completed without errors.
Verified PHP version:
php -v
Output showed:
PHP 8.1.x

## Step 5. Create PHP Test File
Navigate to the web root:
cd /var/www/html
Created a PHP test file:
sudo nano info.php
Added:
<?php
phpinfo();
?>
Saved and exited.

## Step 6. Restart Apache
sudo systemctl restart apache2

## Step 7: Test PHP in Browser
Visited:
http://<my-external-ip>/info.php
The PHP configuration page appeared, confirming PHP was working correctly.

## Step 8: Browser / OS Detector Script
Created:
sudo nano detector.php
Added the provided browser/OS detection code.
Tested in Firefox and confirmed it correctly identified:
    Operating System: Linux
    Browser: Firefox
Outcome successful.

## Outcomes
Apache and PHP are now successfully installed and verified. The browser detection script confirmed proper server-side execution.Client-side programming takes place in a user’s browser; it is information delivered by a server. Server-side programming runs on a web server and contains content that is pushed out to users.

PHP (Hypertext PreProcessor) must be installed on the server because it is a scripting language written for server-side programming operations. Once Apache has been commanded to understand .php files it communicates this process to a browser through HTML. The software then looks back to Apache and processes the .php script.

Configuration order in a directory index is important because it creates a hierarchical priority within searching parameters.
