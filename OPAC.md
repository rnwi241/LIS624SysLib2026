
# 2026-04 Basic OPAC and Cataloging Module Notes

## Overview

Create a bare bones public access catalog (OPAC) and a basic cataloging module in my VM using MySQL,PHP, and Apache software.

## Introduction 

OPAC or Online Public Access Catalog is a digital repository of holdings, most often associated with libraries and informaiton platforms. It primary function is to act as a resource for locating items within database structurs.

OPAC's are maintained through relational databases (cataloging) and accessed by users through search query functions that allow them to locate materials.

## Relational Databases Structures

Relational databases deal with tables of data related to a common subject or field. The structure of relational databases positively impact research because of knowledge tree structures within OPACs.

## Step 1. Create Databases

```sudo mysql -u root```

password: My$ecureP@ssw0rd

```create database NAME;```

```grant all privileges on NAME.* to 'opacuser'@'localhost';```

## Step 2. Create Tables

```mysql -u opacuser -p```

```show databases;```

```use NAMEDB;```

Create Table

```create table NAME```
        example
        example
        example;

Insert Data

```insert into NAME```

Query Data

```select * from SPECIFY```

## Step 3. Database Management

```sudo mysql -u root```

```mysql> show grants for 'opacuser'@'localhost';```

## Step 4. Create Bare Bones OPAC

```mysql -u opacuser -p```

Unders arrow brackets:

```mysql> use opacdb;```
```mysql> alter table books add publication_date date;```
```mysql> update books set publication_date = str_to_date(concat(copyright, '-01-01'), '%Y-%m-%d');```
```mysql> alter table books drop column copyright;```
```mysql> alter table books change publication_date copyright date not null;```

Be sure to check notes on installing mylibrary.html

```sudo nano mylibrary.html```

As well as PHP Search Script

```sudo nano search.php```

## Modification commands

```mysql -u opacuser -p```

```use opacdb;```

## Step 5. Cataloging Module

Access root drive

```cd /var/www/html```

```cd cataloging```

Index.html File

```sudo nano index.html```

PHP Insert Script

```sudo nano insert.php```

## Outcomes

MySQL server had problems with password authentication so that delay my progress for module 10. Once that was fixed, I was able to move through the assignment. However, there appears to be an issue with my PHP search script.

The text within the nano file is the exact match for textbook material, so that still needs to be looked at.

