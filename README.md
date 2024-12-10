<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial covers how to install and set up the help desk system, osTicket.<br />


<h2>Download</h2>

- ### [OsTicket Install Files](https://drive.google.com/drive/u/0/folders/1zBOeA_lLiIJAMPvdahCGLg9wJqVeznbu)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP - Middle man used to communicate between database (sql) and ticketing system (os ticket).
- mySQL - Database used to store data, ticket details, customer information, notes, ect.
- HeidiSQL: database manager uesd to interact within the database
- VC Redist: Used for ticketing system to run properly . ensures the system has the proper c++ libraries to work.
- Rewrite: Clean up URLs and make them more user-friendly. 


<h2>Installation Steps</h2>

<p>
1. Set up virtual machine in azure running windows 10.

2.  install and enable IIS and CGI inside of your VM.
    Go to control panel click "Uninstall a program" then "Turn Windows features on or off" . Click the box for "Internet Information Services" and the plus box next to it. Under "Application Development Features" check the "CGI" box.

3. Create a folder called "PHP" on the c drive

4. Download all files inside of "Osticket Install Files" from top to bottom.
    Right click the Php folder and extract all into the "PHP" folder on the c drive. After this open the c drive, open the inetpub folder, and then the wwwroot folder. Open the osticket folder sepreatley and drag the upload folder from it to inside of wwwroot. Rename the upload folder to "osTicket".

5. Open IIS as admin and register PHP.
    Click "Register new PHP version" open the PHP folder we created on the c drive . select "php-cgi" and  restart your server.

6, Confirm osTicket is running through web server
Go to Sites, Default, osTicket, “Browse *:80”.

7. Enable features and assign permissionsm to osTicket
    Click the drop down arrows until you see the osTicket files we created . Inside of the PHP manager click Enable or disable an extension. Enable php_opcache.dll , php_imap.dll and php_int.dll.
    Inside of the osTicket file in wwwroot , go to include and scroll down to ost-sampleconfig.php and rename to ost-config.php
    Disable inheritance in the properties and add a group for this example we are putting everyone. Apply.


<h2>Complete Install</h2>


osTicket is now successfully installed and should be running smoothly. To connect it to a database :

1. Open HeidiSQL.
   
2. Create a new database for osTicket.

3. Once the database is created, make sure to note down the database name.
In the osTicket enter this database name and the name and password from setting up mysql to complete the connection.
This will allow osTicket to access and store ticketing data in your database, enabling full functionality.
