# 2026-02-26 Installing the Apache Web Server (creating a basic website)

## Overview
Install Appache HTTP web server application on my virtual machine.

Web servers make files accessible to others via their web browsers.

## Step 1. Upgrade VM

```
sudo apt update
sudo apt -y upgrade
```

## Step 2. Install Apache

Specify package:

```
apt search apache2 | head
```

Locate software package:

```
apt show apache2
```

Confirm installation:

```
sudo apt install apache2
```

Status check:

```
systemctl status apache2
```

Results: Confirmed

Loaded: enabled

Active: active/running

## Step 3. Create Web Page

Verify w3m:

```
sudo apt install w3m
```

Loopback to IP address:
```
w3m 127.0.0.1
```

Textual and Markdown Language:

```
cd /var/www/html/
sudo mv index.html index.original.html
sudo nano index.html
```

Link successful:

Apache website

http://34.9.245.31/

## Student Notes from assignment

Commands to located packages:

```
apt search <package_name>
```

```
apt show <package_name>
```

To get to the root directory to make changes via apache use the following steps:

```
cd /var/www/html/
```

```
sudo nano index.html
```

Shift q (Q) to exit, mouse doesn't work with elinks, must use tabs for navigation.

ctrl X (exit) - Y (save)

```
sudo nano index.html
```

## Outcomes

I struggled with putting in the .html code correctly. I forgot to include a closing bracket.

<html> <html>

Should be:

<html> </html>

I successfully updated code to italicize my name with help from Dr. Burns.

Bookmarked his Web Development textbook for future reference.

