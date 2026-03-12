
# 2026-11-03 - Week 9 Installing and Configuring MySQL

## Overview
For this exercise I built a LAMP stack by installing and configuring MySQL and connecting it to PHP. The goal is to understand how a web server, programming language, and relational database work together to store and retrieve information.

## Tasks

1. Install and configure MySQL
2. Run the practice SQL commands 
3. Create the database and table 
4. Create login.php and opac.php 
5. Verify that your page displays the database records

## Step 1. Install and configure MySQL.

Updated system

``` sudo apt update
  sudo apt upgrade
  sudo apt autoremove
  sudo apt clean``

## Step 2. Install MySQL Community Server package
 
```sudo apt install mysql-server```

Confirmed version and functionality.

System status MySQL:
Active (running
   
## Step 4. Created database user and set standards.

Validate passwords: Y
Password validation policy: 0 (zero) for LOW
Remove anonymous users: Y
Disallow root login remotely: Y
Remove test database and access to it: Y
Reload privilege tables now: Y

Access database:

```sudo mysql -u root```

Clear MySQL screen:

```ctrl L```

To quit MySQL:

```\q```

## Step 5. Create User Account

create user 'opacuser'@'localhost' identified by 'noted in personal file';

## Step 6. Create Database

<blockquote>
<p>Notes on the <code>create database</code> command:<br />
The term <code>collate</code> refers to the rules used to compare and sort strings of text.<br />
The character set is set to <code>utf8mb4</code>, which supports the full range of Unicode (e.g., includes emojis, and more).<br />
The <code>0900</code> refers to Unicode 9.0.<br />
The <code>ai</code> refers to accent insenitive, which means that characters like <code>é</code> and <code>e</code> are treated the same for searching and sorting.<br />
The <code>ci</code> refers to case insentivie, which means that a search for <code>Shakespeare</code> also finds <code>shakespeare</code>.Class comments written by Dr. Burns.</p>
</blockquote>

username: opacuser

database name: opacdb

```mysql -u opacuser -p```

```show databases;```

```use opacdb;```

Testing commands for this unit are intuitive. select, update, alter, describe + specification.

## Step 7. Install Php and MySQL Support

Create scripts

```cd /var/www
sudo touch login.php
sudo chmod 640 login.php
sudo chown :www-data login.php
ls -l login.php
sudo nano login.php```

Create file in root directory. 

<html>http://34.9.245.31/opac.php</html>

## Reflection

The correlation between library databases, user policies, and access parameters were evident in this assignment. 
In particular, I found the notes on create database command to be reflective of the searching patterns studied in LIS601 Information Search.
