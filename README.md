<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

This tutorial covers how to install and set up the help desk system, osTicket.<br />

- ### [OsTicket Install Tutorial](https://youtu.be/mzk9p2N_tAY)

<h2>1. Download and Installation Files</h2>
Before getting started, download the necessary osTicket installation files from the link below:

- ### [OsTicket Install Files](https://drive.google.com/drive/u/0/folders/1zBOeA_lLiIJAMPvdahCGLg9wJqVeznbu)

<h2>2. Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>3. Operating System Used </h2>

- Windows 10</b> (21H2)

<h2>4. Prerequisites</h2>

- PHP - Serves as the bridge between the database (MySQL) and osTicket, processing server-side scripts.
- mySQL - Database used to store data, ticket details, customer information, notes, ect.
- HeidiSQL - Database manager uesd to interact within the database
- VC Redist - Used for ticketing system to run properly . ensures the system has the proper c++ libraries to work.
- Rewrite - Clean up URLs and make them more user-friendly. 


<h2>5. Installation Process</h2>

<h3>Step 1: Set up virtual machine </h3>

- Launch a Windows 10 VM on Microsoft Azure and access it via Remote Desktop.

<h3>Step 2: Enable IIS and CGI</h3>

- Go to Control Panel > Programs > Turn Windows features on or off.
- Check Internet Information Services (IIS), and then expand the Application Development Features section.
- Ensure CGI is enabled.

<h3>Step 3: Prepare PHP Folder</h3>

- On the C: drive, create a new folder named PHP.

<h3>Step 4: Download & Extract Files</h3>

- Extract the php files from the downloaded files into the PHP folder on the C: drive.

- Navigate to C:\inetpub\wwwroot, then copy the upload folder from osTicket into this directory. Rename the folder to osTicket.

<h3>Step 5: Register PHP in IIS</h3>

- Open IIS Manager as an administrator.

- Click on PHP Manager and select Register new PHP version.

- Browse to the PHP folder and select php-cgi. Once done, restart your server.

<h3>Step 6: Verify osTicket Installation</h3>

- In IIS Manager, go to Sites > Default Web Site > osTicket, and click on *Browse :80 to test if osTicket is accessible.

<h3>Step 7: Enable Required PHP Extensions</h3>

- Inside the PHP Manager, enable the following extensions:

     - php_opcache.dll
  
     - php_imap.dll

     - php_int.dll
     
- Then, navigate to the osTicket directory in C:\inetpub\wwwroot\osTicket\include, and rename the ost-sampleconfig.php to ost-config.php.

- Right-click on  ost-config.php , go to Properties, and disable inheritance. Assign the Everyone group with full permissions.

<h2>6. Completing the Installation</h2>

- You are now ready to connect osTicket to your MySQL database

<h2>Complete Install</h2>

You are now ready to connect osTicket to your MySQL database.

<h3>Step 1: Create a New Database</h3>

- Open HeidiSQL and create a new database for osTicket.

<h3>Step 2: Configure osTicket to Connect to the Database</h3>

- After the database is created, take note of the database name

- In osTicket enter the database name, username, and password to link osTicket with your MySQL database.

🎉 Congratulations! osTicket is now installed and configured. 🎉
