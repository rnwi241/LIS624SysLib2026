# Apache and PHP Installation Documentation

## Overview

This document records my process installing Apache and PHP on my Ubuntu VM hosted on Google Cloud.  
The goal was to verify that Apache was running and that PHP was correctly configured using a browser/OS detection script.
 
## Environment

- VM Provider: Google Cloud
- OS: Ubuntu 22.04 LTS
- Web Server: Apache 2.4.52
- PHP Version: 8.1
- Browser Used for Testing: Firefox (Linux)

## Step 1: Update Package Lists

First, I updated the package list to ensure I was installing the latest available versions.

```
sudo apt update
This was completed without errors.

## Step 2: Install Apache

sudo apt install apache2

When prompted, I typed Y to confirm installation.

After installation, I checked the status:

systemctl status apache2

Output indicated:

Active: active (running)

This confirmed Apache was running.

## Step 3: Confirm Apache in Browser

I navigated to my VM’s external IP address in the browser:

http://<my-external-ip>

I saw the default Apache2 Ubuntu page, confirming that the server was accessible.

## Step 4: Install PHP

sudo apt install php libapache2-mod-php

Installation completed without errors.

Verified PHP version:

php -v

Output showed:

PHP 8.1.x

## Step 5: Create PHP Test File

Navigated to the web root:

cd /var/www/html

Created a PHP test file:

sudo nano info.php

Added:

<?php
phpinfo();
?>

Saved and exited.

## Step 6: Restart Apache

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

I also tested from my phone, and it correctly detected iOS and Safari.
Issues Encountered
Issue 1: Permission Denied

Initially, I tried creating the PHP file without sudo:

nano info.php

I received a permission denied error.

Solution: Used sudo because /var/www/html is owned by root.
Issue 2: Forgot to Restart Apache

After installing PHP, the test page did not load properly. I realized I had not restarted Apache.

Restarting fixed the issue.
What I Learned

I learned that:

    Installing services is straightforward, but verifying their status is critical.
    The web root directory requires elevated permissions.
    Restarting services after installing modules is often necessary.
    Seeing PHP output in the browser made the connection between server-side processing and client-side display much clearer.

I also realized that documenting as I went made troubleshooting easier because I could retrace my exact commands.

If I repeated this setup, I would:

    Document commands immediately rather than summarizing afterward.
    Keep a second terminal window open for testing while writing notes.

Conclusion

Apache and PHP are now successfully installed and verified. The browser detection script confirmed proper server-side execution.
