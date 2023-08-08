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

- Azure Virtual Machine
- osTicket Installation Files
- Heidi SQL


<h2>Installation Steps</h2>

<p>The first step is creating a VM ( Virtual Machine) using Microsoft Azure Portal. A VM (virtual machine) is a remote computer. In this case, we are using the virtual machine to protect our computer just in case something breaks. We are creating a resource group and the title that I used was “osTicket”.When you are creating your research group you need to make a username and password that you will use for the next step, So you have to remember what it is.  Soon after we create a VM with 4 vCPU equipped with Windows 10. We will the IPv4 in the VM to access it. 
  
 ![B01E5DF0-A141-423D-92C4-6CFABE231901_1_201_a](https://github.com/LuismTejada/osticket-prereqs/assets/140201562/4652fff1-c622-430f-a6e0-66ed97047172)

</p>
<p>
Next, you have to connect to the Virtual machine using Microsoft Remote Desktop, in my case because I am using a MacOS Device. If you are using Windows you will connect with Remote Desktop Connection (RDP). After you download Microsoft Remote Desktop from the app store the connecting part is really simple. You just have to click the (+) at the top. After that, a menu will appear and you have to add the IPv4 in our case "20.25.135.223". You will have to enter the username and password previously created.
</p>
<br />

![D2D997C9-0B49-4E26-A988-81F30A152F81_1_201_a](https://github.com/LuismTejada/osticket-prereqs/assets/140201562/a914b1f1-7f36-4393-b1f8-ef65c80b8215)

<p>
</p>
Finally, you are connected to the VM, now the first step is to enable IIS( Internet Information Systems) just access the control panel and type "Run" and this will open a panel that will give you the ability to view and change system settings. In the run search bar, you will type "control" and this will take you to the control panel.
</p>
<p>  
  
  ![558B13EC-9ED9-4D59-A2D5-B60A9754DA46_1_201_a](https://github.com/LuismTejada/osticket-prereqs/assets/140201562/1ef1e4f6-c1ad-449f-bef8-965047b1068b)


  

After you will click "Programs", and click on “Turn Windows features on or off” That will be under Programs and Features. A list will pop up and then you will enable IIS. After you will expand IIS, click on the WWW(World Wide Web) services -> Application Development Features-> check the box for CGI. Finally, make sure that all of the Common HTTP Features are turned on and click "OK"
</p>
<br />

![568E0857-B335-4BD4-8C05-4BBA3193D6BC_1_201_a](https://github.com/LuismTejada/osticket-prereqs/assets/140201562/b2caa888-973d-4d1e-9efa-0e5d86d4e0f2)

![15E21DEA-37E3-449B-9461-4B7662F38B92_1_201_a](https://github.com/LuismTejada/osticket-prereqs/assets/140201562/87b7f48b-3ed1-4715-9432-ca91f7cbada6)

To make sure that your previous steps work is actually really simple. You just have to go to the browser and open a page, in this page, you will type "127.0.0.1" and press enter. If this did not work you just have to install and  uninstall IIS. 

<img width="1280" alt="Screen Shot 2023-08-07 at 6 58 51 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/e350a567-d4fe-410a-8a11-967fe4ef1d7e">
<p>
<br />
  
From the Installation files download and install PHP Manager for IIS. (PHPManagerforIIS_V1.5.0.msi) and the rewrite module( rewrite_amd64_en-US.msi). After you download PHP you have to double-click "PHP Manager for IIS" You will be clicking "Next" "I Agree" "Next" and "Close". For "rewrite" you have to download it and install, this is very straightforward just click "I Accept" "Install" and "Finish".

<img width="1280" alt="Screen Shot 2023-08-07 at 7 21 44 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/ec37217a-fd3d-41be-915e-413c84851381">

<img width="1280" alt="Screen Shot 2023-08-07 at 7 33 57 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/f8de506e-85a1-49c0-b436-590eed1897f0">

</p>
<br />
The next step will be creating a PHP directory in the C: drive. From the installation files download PHP 7.3.8 (PHP-7.3.8-nuts-Win32-VC15-x86.zip) and unzip the contents into C:\ PHP. The way you unzip the content is by Right Clicking PHP Directory and clicking "Extract All" After you will type "C:\PHP" and all the files will go there. 

<img width="1280" alt="Screen Shot 2023-08-07 at 7 35 59 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/b5cfb588-52ef-465b-be2a-4bcb0ef3c1c5">

<img width="1280" alt="Screen Shot 2023-08-07 at 7 47 34 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/0e37d745-0e84-467f-9b55-ef52ed9fba80">

</p>
<br />


From the Installation Files, download and install VC_redist.x86.exe, Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) a database that osTicket relies on. To download VC Redist is really fast, just have to click "agree" and "install". For MySQL will be a little more complicated, after you download have to double-click on it, and click "Next" to accept the agreement "Next" and you have to do a "Typical Install"

<img width="1280" alt="Screen Shot 2023-08-07 at 7 54 07 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/86b5602f-52dc-4c6d-8a3c-3a3a97221500">

<img width="1280" alt="Screen Shot 2023-08-07 at 8 16 16 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/db9be748-8da4-4772-a243-0f08ff771dcc">
</p>
<br />

Open IIS as an Admin. From the start menu when you type IIS, right-click on IIS and click "Run as admin" 

<img width="1280" alt="Screen Shot 2023-08-07 at 8 23 37 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/098250b1-83e7-49f2-b3c2-046921696513">

Register PHP from within IIS. After that reload IIS (Open IIS and Stop and Start the server)

<img width="1280" alt="Screen Shot 2023-08-07 at 8 25 51 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/3a746c4c-ab57-4925-996f-d2733f11f887"> 

<img width="1280" alt="Screen Shot 2023-08-07 at 8 29 18 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/8df01d08-bcbb-4aa0-bdf1-cd9806b88b2e">

<img width="1280" alt="Screen Shot 2023-08-07 at 8 30 32 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/0bfccafc-8c7c-499c-8d70-31c20f847f74">

From the installation Files, download osTicket v1.15.8. After that extract and copy the "upload" folder to c:\inetpub\wwwroot. Within C:\inetpub\wwwroot, rename "Upload" to "osTicket". After that reload IIS.

<img width="1280" alt="Screen Shot 2023-08-07 at 8 52 11 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/c79ab2ea-9c07-45c6-8597-4097719cd431">

<img width="1280" alt="Screen Shot 2023-08-07 at 8 52 38 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/8eb6fed7-f0e6-4426-984a-a454f01359fa">


The next step is going to Go to Sites-->Default-->osTicket. On the right click “Browse *:80”. An osTicket Installer page will pop up.

<img width="1280" alt="Screen Shot 2023-08-07 at 8 54 59 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/9bfbb756-57b1-4949-8098-7b912cf9ade1">

</p>
<br />

Go back to IIS, click on Sites-->Default-->osTicket. Double-click on PHP Manager and then click on 'Enable or disable an extension'. Enable: php_imap.dll, php_intl.dll and php_opcache.dll. Refresh the osTicket site in your browser and observe the changes.
</p>
<br />

<img width="1280" alt="Screen Shot 2023-08-07 at 8 56 13 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/3648d37e-8546-4668-b955-8263fed14a55">

<img width="1280" alt="Screen Shot 2023-08-07 at 9 00 21 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/c3c8c4dc-7800-455b-b943-586e3a942be1">

<img width="1280" alt="Screen Shot 2023-08-07 at 9 02 47 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/186f0600-f2cb-4512-b64c-c2e6347e65b1">

We need to rename ost-config.PHP. We have to go from C\inetpub\wwwroot\osTicket\include\ost-sampleconfig.PHP to C:\inetpub\wwwroot\osTicket\include\ost-config.php. Permissions need to be assigned to ost-config.PHP. Click the disable inheritance -> Remove all. And then we are going to add new Permissions-> Everyone-> Full control.

<img width="1280" alt="Screen Shot 2023-08-07 at 9 24 57 PM" src="https://github.com/LuismTejada/osticket-prereqs/assets/140201562/241fb21e-4272-40f5-86b9-6cd3de8e82ad">

</p>
<br />

Continue setting up to osTicket in the browser (click continue). Name the Helpdesk and the default email.
</p>
<br />

From the installation files, download and install HeidiSQL. Open HeidiSQL and create a new session and then connect to the session using the username and password when you set up MySQL. After that create a database called "osTicket".
</p>
<br />
We will be continuing to set up osTicket in the browser. Once done finally click on the Install Now button.
</p>
<br />

Finally! If you follow all the steps it should be installed successfully. Make sure to keep everything organized and clean. Delete C\inetpub\wwwroot\osTicket\setup. And set up permissions to read only: C\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>
<br />

Browse to your help desk login page:
C:\inetpub\wwwroot\osTicket\include\ost-config.php. Everything should be working according to plan.
