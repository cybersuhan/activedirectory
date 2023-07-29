<h1>Creating Domain Controller Server</h1>

<h2>Create a Virtual Machine</h2>
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

<h2>Network Settings</h2>
I go to VM Settings -> Network and make the following changes:<br /><br />
<b>Adapter 1:</b> Enable Network Adapter<br />
<b>Attached to:</b> NAT<br /><br />
<b>Adapter 2:</b> Enable Network Adapter<br />
<b>Attached to:</b> Internal Network<br />br />

<h2>Install Windows Server 2019</h2>
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

<b>After Installation, I login to the Server using the password that I created earlier. I rename the PC to "DC".</b>

<h2>Set Up Network Names</h2>
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
4. For the DNS server address, I enter the loopback address:<br />
   <b>Preferred DNS server:</b> "127.0.0.1"<br />
I press OK to save the configuration.<br />
<img src="https://i.imgur.com/WMKVvrk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/46heXyg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
