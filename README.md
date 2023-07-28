<h1>Active Directory in Microsoft Server 2019</h1>

<h2>Description</h2>
In this lab, I create an Active Directory in a virtual environment using Virtualbox. 
<br />


<h2>Tools Used</h2>

- <b>Oracle VirtualBox</b> 
- <b>Windows Server 2019 (for Domain Controller)</b>
- <b>Windows 10 Pro (for Client)</b>

<h2>Network Map</h2>
<img src="https://i.imgur.com/rKLa7Li.png" />

<h2>Before Starting</h2>
Before starting the project, I downloaded Windows Server 2019 and Windows 10 iso files. I also had Virtualbox 7.0 installed in my computer.  
<h2>Walk-through:</h2>


<h3>Windows Server 2019</h3>

<h4>Create a Virtual Machine</h4>
I created a new VM and used following configuration:<br />
<b>Name:</b> "DC"<br />
<b>Folder:</b> "<i>Selected a folder where the VM is to be saved</i>"<br />
<b>ISO Image:</b> "<i>Selected the Server 2019 ISO image that I downloaded</i>"<br />
<b>Base memory:</b> "2048 MB"<br />
<b>Processors:</b> "2"<br />
<b>Virtual Hard Disk:</b> "Create New, 50.00 GB"<br /><br />
<img src="https://i.imgur.com/b1tGPRd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/EJRoi1V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/HwDImLc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/jNEyOm2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

<h4>Network Settings</h4>
I go to VM Settings -> Network and make the following changes:<br /><br />
<b>Adapter 1:</b> Enable Network Adapter<br />
<b>Attached to:</b> NAT<br /><br />
<b>Adapter 2:</b> Enable Network Adapter<br />
<b>Attached to:</b> Internal Network<br />br />

<h4>Install Windows Server 2019</h4>
I start the DC VM in virtualbox. I take the following Steps:<br /><br />
1. <b>Language:</b> "English" -> <i>Next</i><br />
2. <b>OS to install: </b>Windows Server 2019 Standard Evaluation (Desktop Experience) -> <i>Next</i><br />
3. <b>Type of Installation: </b>"Custom" -> <i>Next</i><br />
4. Allocate the only unallocated space -> <i>Next</i><br />
5. <b>Administrator Password:</b> "CyberSuhanLab123" -> <i>Finish</i><br />
<img src="https://i.imgur.com/dAARK98.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/zWqN3BF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/NeAaJxC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/bf2YqTZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/IAYYZwy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/ZnwZ1YB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

After Installation, I login to the Server using the password that I created earlier. I rename the PC to "DC".

<h4>Set Up Network Names</h4>
As I configured before, the Windows server VM has 2 network adapters connected to it. When I go to the Network Adapter settings, I can see both of the network adapters. <br />
<img src="https://i.imgur.com/YjNfYul.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
I find the one that is connected to the internet. This is the NAT network. I change the name of the adapter to ```INTERNET```.<br />
The other adapter is meant to be the Internal Network Adapter. I change it's name to ```INTERNAL```.<br />
<img src="https://i.imgur.com/up9smQ4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

After changing the names, I assign an IP address to the "INTERNAL" network. To do that, I take the following steps:<br />
1. Right-Click the "Internal" Adapter and click "Properties"<br />
2. Double-Click on IPv4 (Internet Protocol Version 4 TCP/IPV4)<br />
3. Turn on "Use the following IP adress:"<br />
   a. <b>IP address:</b> "172.16.0.1"<br />
   b. <b>Subnet mask:</b> "255.255.255.0"<br />
4. For the DNS server address, I input the loopback address:<br />
   <b>Preferred DNS server:</b> "127.0.0.1"<br />
I press OK to save the configuration.<br />
<img src="https://i.imgur.com/ktlfOR5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/K9mDrqe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

<h4>Creating a Domain</h4>
Next step is to create an Active Directory Domain Name. To do this, I open the Server Manager and take the following steps:<br />
1. Click on "Add roles and features"<br />
2. Select "Role based or feature-based installation" -> <i>Next</i><br />
3. Select Destination server -> <i>Next</i><br />
4. In Server roles, tick "Active Directory Domain Services", Click "Add Features" -> <i>Next</i><br />
5. In Features, keep default settings -> <i>Next</i><br />
6. Click "Install"<br />

<img src="https://i.imgur.com/peY3HtV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/C99RndX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/PHszii4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/6py1gvu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/tQ3a7w2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/nTjSCzK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/wZXIhAl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

After the installation, I need to work on the post-deployment configuration. To do this, I take the following steps:<br />
1. Click on the Flag icon on the top right<br />
2. Turn on "Add a new forest" and for the root domain name, enter "suhancyberlabs.com" -> <i>Next</i><br />
3. In Domain Controller Options, I enter a password. (I dont use this password anywhere in this lab) -> <i>Next</i><br />
4. In DNS Options, I dont change anything, I just "click" Next on everything else and finally "Install" <i>Next</i><br />
After Installation, The VM restarts automatically. <br />
<img src="https://i.imgur.com/f6Vv20c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/yazW7X4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/jS6xwzt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

After the VM restarts, The Domain Name is shown before the Account Name:<br />
<img src="https://i.imgur.com/FWsZFf4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />














<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
