<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP Manager
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86
- MYSQL.505.62

<h2>Installation Steps</h2>

<p>
Welcome to the first section of the IT tutorial. In this section, you will create a Virtual Machine (VM), a remote computer, using the Microsoft Azure portal (portal.azure.com). Once you log into Azure, go to virtual machines and select Create. For resource group, create a new resource group and name it osTicket. Name your virtual machine. I called it similar to the resource osticket-vm. Next, pick a region for your VM. In Image, select  Windows 10 Pro, version 22H2 - x64 Gen 2. For the size of the CPU, make sure it is between 2 - 4 CPUs.  After selecting the size of your CPUs, create a username and password to log into the virtual machine. I recommend using Notepad to keep track of the username and passwords for this tutorial. Make sure to check under licensing to confirm, then select Review-Create.
</p>

![Screenshot 2025-01-13 093033](https://github.com/user-attachments/assets/69f98f2c-134f-4bf0-ab27-214f552dce5b)
![Screenshot 2025-01-13 093140](https://github.com/user-attachments/assets/7ce3848c-c459-4b4b-a106-4c30b1cbeaeb)
![Screenshot 2025-01-13 093206](https://github.com/user-attachments/assets/73c9a7bc-a54d-41d0-91cb-88ace9d2608a)

<p>
Once the Virtual Machine is deployed, copy the public IP address, go to your desktop, and connect to the Remote Desktop Connection. If you are a Mac user, you can use Microsoft Remote Desktop.
</p>
<br />

<p>

![Screenshot 2025-01-13 184724](https://github.com/user-attachments/assets/8c5d1eba-d724-42bd-8361-883e9b0feca5)
![Screenshot 2025-01-13 102959](https://github.com/user-attachments/assets/e1b546aa-2695-4e6c-b0ca-b530bc0c1671)

</p>
<p>
Copy, paste, or type in your virtual machine's public IP address and select Connect. Then, enter the username and password you created when setting up the virtual machine. Once you log in, we will download the osTicket-Installation-File.zip. Here is the link for the osTicket files: osTicket-Installation-Files.zip
</p>
<br />
<p>
We will install all the dependencies needed to install OSTicket work, which runs on the web browser. It requires a web server and a database to be installed and configured.

Open the link in your remote desktop web browser and download the files. Then, drag the zip file to your remote desktop and unzip the files. 
</p>
<br />

<p>
  
![Screenshot 2025-01-13 103737](https://github.com/user-attachments/assets/7a9e859c-ee23-41fd-ac26-da64de9d56f1)

</p>
<p>
Great. We are going to install and enable IIS in Windows with CGI. Go to the Start menu, select Control Panel > Programs>  (to the left), and select Windows features on or off. Check the box that says Internet Information Services (IIS), and then click the plus button to expand the list. Go to World Wide Web Services  > Application Development Features, check the CGI box, and then hit OK.
</p>
<br />

<p>
  
![Screenshot 2025-01-13 104427](https://github.com/user-attachments/assets/a9e7c2f8-7908-46c9-9e0c-7cf9f842b35e)

</p>

<p>
The next step is to install all the dependencies for the osTicket to run from the osTicket file, which we unzip to the desktop. Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and the Rewrite Module(rewrite_arm64_en-US.msi). Create a folder called PHP on the C drive. Back into the osTicket folder, unzip PHP 7.3.8 (php-7.3.8—nts-Win32-VC15-x86.zip) in the C: PHP folder we made previously.
</p>
<br />

<p>
  
![Screenshot 2025-01-13 104855](https://github.com/user-attachments/assets/6221cfeb-3558-4952-bca8-7badb0a61e54)

![Screenshot 2025-01-13 104958](https://github.com/user-attachments/assets/b2304ca7-f157-4e8e-8516-7182f021fb8e)

![Screenshot 2025-01-13 105146](https://github.com/user-attachments/assets/c17c468a-f252-4fef-86d8-19c345aa6381)



</p>
<p>
 Next, install VC_redist.x86.exe. Finally, install MYSQL.5.5.62 (mysql-5.5.62-win32.msi), a database that osTicket uses for the user accounts, ticketing information, and everything done in the ticketing system. While installing, choose Typical Setup. Once finished installing, launch the MySQL server and select Configuration Standard. When you reach the security option, create a username and password. Please write down the username and password for the MySQL server.
</p>
<br />

<p>
  
![Screenshot 2025-01-13 105626](https://github.com/user-attachments/assets/f90a8658-7010-483b-84b0-8c9af00a30cb)

![Screenshot 2025-01-13 105745](https://github.com/user-attachments/assets/60d8728c-7865-43e3-b855-d5648ab3b7e1)

</p>
<p>
Once you have finished the MySQL configuration, open Windows Start, type in Internet Information Services (IIS), and run as an administrator. Open the PHP Manager, click Register new PHP version, browse the C drive to the PHP folder, select php-cgi.exe, and then hit OK. Go back to the IIS home page, stop the server, and then start it again.
</p>
<br />
<p>
  
![Screenshot 2025-01-13 110311](https://github.com/user-attachments/assets/8421b81c-606e-4023-969e-e8fd458a9b93)

![Screenshot 2025-01-13 110433](https://github.com/user-attachments/assets/ab6c78fe-7bfa-4ff9-b235-da2a8ba9c5bd)

![Screenshot 2025-01-13 110519](https://github.com/user-attachments/assets/6fee048b-9bd2-4f03-9a51-c0d7c7f58c15)

![Screenshot 2025-01-13 110554](https://github.com/user-attachments/assets/202db69e-2e49-4644-98ff-12e2eaf5cd01)

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
  
![Screenshot 2025-01-13 105626](https://github.com/user-attachments/assets/f90a8658-7010-483b-84b0-8c9af00a30cb)

![Screenshot 2025-01-13 105745](https://github.com/user-attachments/assets/60d8728c-7865-43e3-b855-d5648ab3b7e1)

</p>
<p>
Extract the osTicket file, copy the upload folder to " C:\inetpub\wwwroot,” and rename the upload to “osTicket.”
</p>
<br />

<p>
  
![Screenshot 2025-01-13 111115](https://github.com/user-attachments/assets/4c49f30e-f456-47dd-abde-c20747e3a96e)

![Screenshot 2025-01-13 111157](https://github.com/user-attachments/assets/7e4c110b-4c21-4c87-8738-8cdc9efbd2de)

</p>
<p>
In the IIS Manager, stop and start the server again. Inside the IIS Manager on the left side, go to Sites > Default > osTicket.  On the right side, select “Browse*.80”(http).
</p>
<br />

<p>

![Screenshot 2025-01-13 111458](https://github.com/user-attachments/assets/0c21d6c0-fb9d-48ac-bcc9-090c03d421a3)

![Screenshot 2025-01-13 111533](https://github.com/user-attachments/assets/18e280af-ab45-406b-9e5e-0df3b643ee8a)

</p>
<p>
Some extensions are not enabled in the osTicket Installer; therefore, we will install them using the IIS Manager. Once in the IIS Manager, go to Sites > Default > osTicket. Select PHP Manager and click on “Enable or disable an extension.” In the PHP extension list, enable “php_imap.dll,” “php_intl.dll”, and “php_opcache.dll.” Refresh the osTicket web server, and the extension should be enabled.
</p>
<br />

<p>

![Screenshot 2025-01-13 111837](https://github.com/user-attachments/assets/34976d71-f928-43d3-bdf5-ac0ad9696575)

![Screenshot 2025-01-13 112041](https://github.com/user-attachments/assets/309891e3-33ab-4f17-89bc-d2170fc6fb5c)

![Screenshot 2025-01-13 112157](https://github.com/user-attachments/assets/1ae09df3-52e2-4a27-9cdf-ed7086971166)
  
</p>
<p>
In the C drive, rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to
C:\inetpub\wwwroot\osTicket\include\ost-config.php. Assign Permissions to ost-config.php by right-clicking it to open properties, select security, and go to advanced. Disable Inheritance, then Add New Permission, Select principle, type in everyone, select Full Control, then hit Apply and OK.
  
</p>
<br />

<p>

![Screenshot 2025-01-13 112428](https://github.com/user-attachments/assets/03b077e2-1bd9-4fbe-9186-341ce8021b1a)

![Screenshot 2025-01-13 112556](https://github.com/user-attachments/assets/4938721b-d2c1-4e31-bd8f-e27636d3aa22)

![Screenshot 2025-01-13 112706](https://github.com/user-attachments/assets/0d54486e-ac7a-417f-ab71-f2fe46ba0026)
 
</p>
<p>
  
Once we finish the osTicket configurations and extensions, we will continue setting up the osTicket in the web browser by clicking Continue. Name the Helpdesk, select the default email address, and fill in Admin User ( note the email for the default and admin can not be the same).

</p>
<br />

<p>
  
</p>
<p>
  
</p>
<br />

