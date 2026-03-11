
## 2026-11-03 - Week 9 Installing and Configuring MySQL
Task

    Install and configure MySQL
        Update your system.
        Install mysql-server.
        Confirm the version and verify the service is running.
        Run mysql_secure_installation.

    Create a database and user

    From the MySQL command line:
        Create a user named opacuser.
        Create a database named opacdb.
        Grant privileges to opacuser.

    Create and populate a table
        Create the books table described in the lecture.
        Insert the example book records.

    Practice MySQL commands

    Run all practice commands listed in the lecture from the mysql> prompt. These include SELECT, UPDATE, ALTER, DELETE, and INSERT statements.

    Install PHP–MySQL support

    Install the PHP module that allows PHP to communicate with MySQL and restart the services.

    Create the database login file

    Create:

    /var/www/login.php

    Add the credentials for opacuser and set the permissions as shown in the lecture.

    Create the OPAC PHP page

    Create:

    /var/www/html/opac.php

    Add the PHP and HTML code provided in the lecture.

    Test your code

    Run the PHP syntax tests and then visit your server’s public IP address in a browser. If everything worked correctly, you should see data from your database displayed on the webpage.
________________________________________
Overview of assignment:
