<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Virtual Machine in Azure
- Install osTicket v1.15.8
- Install HeidiSQL
- Install MySQL
- Install PHP

<h2>Installation Steps</h2>
<h2>Create an Azure Virtual Machine Windows 10</h2>
  
<p>
We will need to login in to Azure to create a Windows virtual machine, it will be named, osticket-vm. 

![1](https://github.com/user-attachments/assets/e9a2ab97-d744-4257-a089-3a53380bbe90)
<p>
We also need to configure the admin credentials, after that we will launch the virtual macine from our desktop. 
  
![2](https://github.com/user-attachments/assets/1d28d36b-17cd-4003-8b57-3a97bccaa29d)
<p>

![4](https://github.com/user-attachments/assets/de9fbf19-07f4-4720-9ecd-e73564347e26)
<p>
Once we are in our Windows virtual machine we will download the file for the osTicket system and unzip all of the files.

![5](https://github.com/user-attachments/assets/9333bfe4-59e3-4eb8-a6b8-2435aa323d15)
<p>
Next we are going to enable IIS(Internet Information Services) with CGI, which will serve up the osTicket program.

![6](https://github.com/user-attachments/assets/8b677da2-6998-4042-8aa6-feea19d669b7)
<p>
Install PHP Manager for IIS 
  
![7](https://github.com/user-attachments/assets/f33944b3-1c2a-4715-a1ec-610f9df23169)
<p>
Install the Rewrite Module

![8](https://github.com/user-attachments/assets/d4cb9781-8753-45c8-80a2-b20e9ad3a0fe)
<p>
Create the directory C:\PHP
<p>
We are going to extract the files in the PHP file from the osTicket instllation files onto the Windows(C:).

![9](https://github.com/user-attachments/assets/dec747e7-36fb-42fb-83b8-cee7fecd0734)
<p>
Install C++ Redistrbutable(x86)

![10](https://github.com/user-attachments/assets/f39206f9-e332-4a0e-89f5-b3107b3b681c)
<p>
Install MySQL
<p>
Once this is installed it will ask you to create a username and password, it is essentail you keep track of that information. 
  
![11](https://github.com/user-attachments/assets/b44dc73b-ed00-4c01-9a4f-7c7972654901)
<p>
Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
<p>
Reload IIS (Open IIS, Stop and Start the server)
  
![12](https://github.com/user-attachments/assets/b2b7243e-15ac-40ea-892d-3bc95906de7a)
<p>
Install osTicket v1.15.8
<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
<p>
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
<p>

![13](https://github.com/user-attachments/assets/7bbfcf07-5276-466f-a290-c94c4a58c1fa)
<p>
Reload IIS (Open IIS, Stop and Start the server)
<p>
Go to sites -> Default -> osTicket
<p>
On the right, click “Browse *:80”. Now osTicket will launch in the browser. 

![14](https://github.com/user-attachments/assets/39d2705c-ecde-42a5-9b75-ee706763901d)
<p>
Some extensions are not enabled, and we will enable them. 
We will go back to IIS, sites -> Default -> osTicket. Double-click PHP Manager. Click “Enable or disable an extension”.
<p>
Enable: php_imap.dll, Enable: php_intl.dll, Enable: php_opcache.dll.
<p>
Refresh the osTicket site in your browser, those extensions should now have the green checkmark. 
<p>

![15](https://github.com/user-attachments/assets/b7977e9b-cbdc-4773-88ef-8705b3ca587d)
<p>
Next we will tackle the Permissions, so osTciket can be able to make changes in the backend. Assign Permissions: ost-config.php. Disable inheritance -> Remove All. New Permissions -> Everyone -> All

![16](https://github.com/user-attachments/assets/2e66e538-cec3-4f8f-8262-30ec614a4f9a)
<p>
  
![17](https://github.com/user-attachments/assets/8634cced-a4b2-4d01-a454-fa648d5adca2)
<p>
Install HeidiSQL, and connect to the session.

![18](https://github.com/user-attachments/assets/ea01215a-608a-4cfb-873c-cb17f654de25)
<p>
  
![19](https://github.com/user-attachments/assets/83fb1fba-0b68-427f-b346-8aa6a2b8ffb3)
<p>
The username and password is the one that was configured when MySQL was installed. 
  
![20](https://github.com/user-attachments/assets/ee719447-01c5-4d1b-96bd-0878c5e7a82a)
<p>
Finish the setup of osTicket

![21](https://github.com/user-attachments/assets/d20f4d2a-59da-4429-b055-406e54a0ec29)

<br />
