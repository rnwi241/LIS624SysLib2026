## Koha Install Quick Notes

Koha is an open source llibrary management system, more commonly called an integrated library system (ILS).

# Step 1. Create new instance in Google Cloud

Machine Configuration: e2-medium (2 vCPU, 1 core, 4 GB memory)
OS and storage: Ubuntu 24.04 LTS, 20GB Hard Disk
Networking:

```Allow HTTP traffic```
Network Tag:

```koha-staff-8080```
```koha-opac-8081```

# Step 2. Configure Firewall Ports

Firewall Rule 1: Port 8080

Click on the three line menu in left tophand corner.
Click on VPC Network.
Click on Firewall.
At the top of the page, choose Create a firewall rule (Do not choose Create a firewall policy):

    Add name: koha-staff-8080
    Add description: Open port 8080 for the Koha staff interface

Next to Targets, click on Specified target tags.
In Target tags, add our tag name: koha-staff-8080.
In the Source IPv4 ranges, we allow access from anywhere (0.0.0.0/0) to simplify setup. In a real deployment, we might want to restrict administrative access to port 8080 to specific IP addresses.
Click on Specified protocols and ports

    Click on TCP
    Add 8080 in the Ports box

Click on Create

Firewall Rule 2: Port 8081

Create a second firewall rule

    Add name: koha-opac-8081
    Add description: Open port 8081 for the Koha opac interface

Next to Targets, click on Specified target tags.
In Target tags, add our tag name: koha-opac-8081.
In the Source IPv4 ranges, we allow access from anywhere (0.0.0.0/0) to simplify setup. In a real deployment, we may or may not want to restrict public access to port 8081 to specific IP addresses.
Click on Specified protocols and ports

    Click on TCP
    Add 8081 in the Ports box

Click on Create

Note: These rule must match the ports in Koha and Apache. 

# Step 3. Install Koha

Note: Working in tmux will re-open a session if you get disconnected. 

```tmux```

```tmux attach```

# Step 4. Servicer Setup

```sudo apt update```

```sudo apt upgrade```

```sudo apt autoremove -y && sudo apt clean```

# Step 5. Add Koha Respository

Run the following three commands to set up the signing keys.

```sudo apt install apt-transport-https ca-certificates curl```

```sudo mkdir -p --mode=0755 /etc/apt/keyrings```

```sudo curl -fsSL https://debian.koha-community.org/koha/gpg.asc -o /etc/apt/keyrings/koha.asc```

# Step 6. Install MariaDB

```sudo apt update```

```sudo apt install mariadb-server```

# Step 7. Install Koha

```sudo apt update```

```apt show koha-common```

```sudo apt install koha-common```

# Step 8. Opening Ports

To make sure our staff interface and public interface are accessible we specify the ports.

```sudo cp /etc/koha/koha-sites.conf /etc/koha/koha-sites.conf.backup```

Using the text editor

```sudo nano /etc/koha/koha-sites.conf```

Reconfigure to the following:

INTRAPORT="8080"
OPACPORT="8081"

# Step 9. Apache2 Setup

Ensure that Apache2 modules are enabled for Koha.

```sudo a2enmod rewrite cgi headers proxy_http```

```sudo systemctl restart apache2```

Be sure to back up your files!

```sudo cp /etc/apache2/ports.conf /etc/apache2/ports.conf.backup```

Reopen your text editor, under LISTEN add the following:

```sudo nano /etc/apache2/ports.conf```

Add

LISTEN 8080
LISTEN 8081

# Step 10. Create Koha Instance

```sudo koha-create --create-db bibliolib```

```sudo systemctl restart apache2```

# Step 11. Add Additional Apache2 Configurations

```sudo a2dissite 000-default```

```sudo a2enmod deflate```

```sudo a2ensite bibliolib```


```sudo systemctl reload apache2```

```sudo systemctl restart apache2```

# Step 12. Koha Web Installer

```sudo koha-passwd bibliolib```

Note the output will be unique to you. Be sure to document the username and password returned. 

Vist your IP address with :8080 added. 

Create an Administrator Identity. 

Note: Be sure to use the Web Installer Instructions

# Step 13. Ensure Public OPAC is working.

<html>http://34.61.95.44:8081/</html>

# Outcomes

Koha was successfully installed. 


