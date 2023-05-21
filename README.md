# ostickp align="center">
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

- Azure Tenant
- Subsricption
- Google Drive Instalation Files

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/FomqDzE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will first start by creating a rescource group in Microsoft Azure. Click on rescource group or search rescource in the search bar. Choose a name and a region. After that has been done, we will next create a Virtual Machine in the rescource group.  
</p>
<br />

<p>
<img src="https://i.imgur.com/WmdqTCR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Type in the search bar for "Virtual Machine" and click on it. Make sure to select the rescource group we just made. Give the machine a name, choose the same location as the recource group. Under the image section choose Windows 10 Pro. Next step is to choose what size or components the virtual machine will run off. I recomend at least the 2 cpu 16 memory. Click next for disk and network. It will automatically create a virtual network and subnet. Click review and create.
</p>
<br />

<p>
<img src="https://i.imgur.com/acYzEsC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we are going to launch windows in the virtual desktop. Click on the virtual machine we just made and copy the Public IP address. There is a copy icon to the right of the IP address. Go to the search bar near the start window and search for remote desktop. Paste the IP address in the Computer section of Remote Desktop. Type in user name and password you just made. Once it starts up, say no to all the settings it pops up with. Next we are going to setup ISS in windows. 
</p>
<br />

<p>
<img src="https://i.imgur.com/9klNbCg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Microsoft Edge and paste the Google Drive Installation in an open tab. Go to the Search near start button and type Control Panel and click on it. Click on Uninstall a program. CLick on the Turn Windows features on or off. Search for Internet Information Services and selct the box and click ok.
</p>
<br />

<p>
<img src="https://i.imgur.com/mzR2Njg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
It should have Created a folder path from the image above with the wwwroot. Install the WebPlatforminstaller from the Google Drive Instalation Files. Once it is installed, go to the search and search for Web Platformer and open it. Once it is opened go to the search bar on the top right and type MySQL. Click on Add from MySQL WIndows. Next we will add PHP files. Type in the search for PHP and on Name to view search results by name. Add all PHP x86 files starting with the 5.6.31 to 7.3.25(x86). Click on Install.
</p>
<br />
<p>
<img src="https://i.imgur.com/VRe6m4E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A popup window will ask you to create an admin accout password. The admin name will be root and you just create a password. Click on I accept and it will attempt to download files.
</p>
<br />

<p>
<img src="https://i.imgur.com/WAcwZFS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
For any of the files that fail, refer to the Google Drive files for any that failed. Next you will download the osTicket file from the Google Drive files. It will end up in your Downloads Folder. Right click it and Extract All in the downloads folder. Once that is complete, click on the osTicket folder and copy the "upload" folder in there to the folder we navigated to earlier c:\inetpub\wwwroot. Rename the "upload" folder to "osTicket".
</p>
<br />

<p>
<img src="https://i.imgur.com/CHdgKTZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will now be reloading IIS. Go to the search next to start and search IIS. On the right side click on the restart button. On the left side of IIS, click on the vm-osticket right facing arrow. Then do the same for Sites, Default Web Site and click on the osTicket folder. On the right side click on "Browse*:80(http). This will open a webbrowser to osTicket. Back in IIS, go back to and click on the osTicket folder. Click on PHP Manager at the center top. Click on "Enable or disable an extension". Right click and Enable "php_imap.dll", "php_int.dll", and "php_opcache.dll". Hit the reload button on the osTicket browser and see that the Intl Extension is checked off.
</p>
<br />

<p>
<img src="https://i.imgur.com/2sG2kVs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we will navigate to the osTicket folder in the file explorer. Go to c:\inetpub\wwwroot\osTicket\include. Find the file named "ost-sampleconfig" and rename it to "ost-config". Right click that file and select properties. Select "Security" and then "Advanced". Click on "Disable inheritance". Selct "Remove all inherited permissions from this object". Then click on "Add" since we will be adding our own permissions. Click on "Select a principle". Click in the box saying to Enter the object name to select. Type the word "Everyone" and click "check names" and ok. It will bring you to the permissions and select the box "Full Control". Then select "Apply" and "ok"
</p>
<br />

<p>![image](https://github.com/TH0dge/osticket-prereqs/assets/132714490/2970c2f0-4e25-40d9-8032-89a437212014)
</p>
<p>
Go back to osTicket webpage. Click on "continue". It now works.If that last section wasn't done properly, then it would no open. Fill in the information. Make sure "Default Email" is a different email then "Email Address" under the Admin User section. Go back to the Google Drive files and download HeidiSQL. It should bring you to document and click on the link to download the HeidiSQL. Click on either "Open File" from the website or navigate to the "Downloads" folder and double click HeidiSQL Application. Click Accept Install nexty and Install. Then click Launch and it will open. 
</p>
<br />

<p>
<img src="https://i.imgur.com/ofhYaNm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
AT the bottom left of HeidiSQL click on "New" and on the right side under "root" enter the password and click "open". It will then take you to the data bases and has some default data bases in there. You are going to right click "unnamed" and slect "Create new" and "Database". Type in the box "osTicket" and click create. .  
</p>
<br />

<p>
<img src="https://i.imgur.com/x13MPPn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to the webpage with osTicket and under "MySQL Database" type osTicket. Under MySQL Username type "root" and then under MySQL Password type the password you had for root
</p>
<br />

<p>
<img src="https://i.imgur.com/Nsa2Uqa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
os Ticket should now be installed. There are some cleanup things to do before closing out. Go to C:\inetpub\wwwroots\osTicket\setup and delete the Setup folder. If it doesn't let you delete the folder, go into the folder and delete all the contents and then go back and you should be able to delete the folder. In the same place click on "include" and find ost-config.php and right click and select properties. Click on Security and select "Advanced" Click on the permission and at the bottom select "Edit". Uncheck all the boxes except for "Read" and "Read and Execute". Click on "Apply" at the bottom and click on "Ok".
</p>
<br />

<p>
In our next section, we will be setting up osTicket with new Roles, Agents, Permissions, Users, and SLAs.
</p>
<br />et-prereqs
