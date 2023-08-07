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
From the Installation files download and install PHP Manager for IIS. (PHPManagerforIIS_V1.5.0.msi) and the rewrite module( rewrite_amd64_en-US.msi)
</p>
<br />
The next step will be creating a PHP directory in the C: drive. From the installation files download PHP 7.3.8 (PHP-7.3.8-nuts-Win32-VC15-x86.zip) and unzip the contents into C:\ PHP.
</p>
<br />

From the Installation Files, download osTicket v1.15.8. After that extract and copy the "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, rename "upload" to "osTicket". After that reload IIS (Open IIS and Stop and Start the server).
</p>
<br />


The next step is going to Go to Sites-->Default-->osTicket. On the right click “Browse *:80”. An osTicket Installer page will pop up.
</p>
<br />

Go back to IIS, click on Sites-->Default-->osTicket. Double-click on PHP Manager and then click on 'Enable or disable an extension'. Enable: php_imap.dll, php_intl.dll and php_opcache.dll. Refresh the osTicket site in your browser and observe the changes.
</p>
<br />

We need to rename ost-config.PHP. We have to go from C\inetpub\wwwroot\osTicket\include\ost-sampleconfig.PHP to C:\inetpub\wwwroot\osTicket\include\ost-config.php. Permissions need to be assigned to ost-config.PHP. Click the disable inheritance -> Remove all. And then we are going to add new Permissions-> Everyone-> Full control.
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
