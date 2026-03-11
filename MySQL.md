
# 2026-11-03 - Week 9 Installing and Configuring MySQL

## Overview
For this exercise I built a LAMP stack by installing and configuring MySQL and connecting it to PHP. The goal is to understand how a web server, programming language, and relational database work together to store and retrieve information.

## Tasks
1. Install and configure MySQL, 
2. Run the practice SQL commands, 
3. Create the database and table, 
4. Create login.php and opac.php, 
5. Verify that your page displays the database records

## Step 1. Install and configure MySQL.
Updated system
  * sudo apt update
  * sudo apt upgrade
 * sudo apt autoremove
 * sudo apt clean

## Step 2. Install MySQL Community Server package 
sudo apt install mysql-server
Confirmed version and functionality.
   
## Step 4. Created database user and set standards.
Validate passwords: Y
Password validation policy: 0 (zero) for LOW
Remove anonymous users: Y
Disallow root login remotely: Y
Remove test database and access to it: Y
Reload privilege tables now: Y

## Step 5. Creating Tables
