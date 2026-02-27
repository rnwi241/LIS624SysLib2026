# LIS624-201 Systems Librarianship
Tools for understanding systems librarianship.
This repository will be used to document my educational understanding of how technologies impact information ecosystems.
___
## 2026-02-05 - Module 2.4 Documenting with Git, GitHub, and Markdown for Docs
Goal: Understand Text Editor using Microsoft Edit, create a GitHub account, establish GitHub repository, Git Configuraiton completion, generate SSH keys, perform clone, edit, and push functions to GitHub via VM. Post reflection to discussion board.

Context: These tasks are associated with module 4 in LIS624-201.

Steps: Outlined in goals.

Results: Completed.

Verification: See grades in Canvas.

Notes: Selected Microsoft Edit for text editor. 'edit' will launch text editor, ctrl-q will exit. 
__
## 2026-02-10 Module 3.1 Searching with Grep
Goal: Search with grep, upload BibTeX file to VM using Web of Science data. Use command prompts to search for data specs. 

Context: These tasks are associated with module 5 in LIS624-201.

Steps: Outlined in goals.

Results: Completed.

Verification: See grades in Canvas.

Notes: 'sudo reboot' to restart the system.'ZZ' command will save & quit (exit) out of the text editor. cat operating-systems.csv will bring you back. 'man grep' reference manual. Connection link is done by connecting to the SSH-browser.
__
## 2026-02-16 Module 3.2 Managing Software & 3.3 Library Search
Goal: Use 'sudo' and 'apt' commands to manage software and package applications. Install 'yaz' client and use it to search UK's InfoKat OPAC. 

Context: 'Yaz' is used to search bibliographic attributes (metadata fields) in Online Public Access Catalogs (OPAC's). 

Steps: 1. Update and upgrade software using sudo/apt commands on VM. 2. Install 'yaz' client and search metadata records.

Results: Completed.

Verification: See grades in Canvas. 

Notes: 

To keep system up-to-date:
* sudo apt update
* sudo apt upgrade
* sudo apt autoremove
* sudo apt clean

Yaz command for Bib-1 attributes: 'man bib1-attr'

LOC Bibliographic-1 Attribute Set: https://loc.gov/z3950/agency/defns/bib1.html. 
__
## Command Line Notes & Cheat Codes
* list files and directories.................. ls
* print name of current/working directory..... pwd
* create a new directory...................... mkdir
* remove or delete an empty directory......... rmdir
* change directory............................ cd
* create an empty file........................ touch
* print characters to output.................. echo
* display contents of a text file............. cat
* copy a file or directory.................... cp
* move or rename a file or directory.......... mv
* remove or delete a file or directory........ rm
* restart.......sudo reboot
* update system...sudo apt update/ sudo apt -y upgrade
____  
## Module 4.7 2026-02-26 Installing the Apache Web Server (creating a basic website)
Goal: Install Appache web server on my virtual machine.

Context:Identify IP addresses with software products. Command ip a will give you the personal IP address of your website, elinks http://10.128.0.2 (internal) 

Steps: When installing apache softward <systemctl status apache2> ensure status reflection <Loaded: enabled> and <Active: active/running>.


Results: Installed with elinks, loop back IP address is elinks localhost.


Verification: See grades in Canvas.

Notes: apt search <package_name> and apt show <package_name> commands locate desired packages.
* shift q (Q) to exit, mouse doesn't work with elinks, must use tabs for navigation.

## Module 4.7 2026-02-26 Installing the Apache Web Server (creating a basic website)
Goal: Install Appache web server on my virtual machine.

Context: Identify IP addresses with software products. Command 'ip' a will give you the personal IP address of your website, 'elinks http://10.128.0.2' (internal). A web server is software that makes websites available in browsers. As noted in our reading for the week, web servers make files accessible to others via their web browsers. 

Steps: When installing apache softward 'systemctl status apache2' ensure status reflection <Loaded: enabled> and <Active: active/running>.

Results: Installed with elinks, loop back IP address is 'elinks localhost'.

Verification: See grades in Canvas.

Notes: apt search <package_name> and apt show <package_name> commands locate desired packages.
* shift q (Q) to exit, mouse doesn't work with elinks, must use tabs for navigation.
* sudo nano index.html - ctrl X (exit) - Y (save)
* Apache website http://34.9.245.31/

To get to the root directory to make changes via apache use the following:
cd /var/www/html/
sudo nano index.html
