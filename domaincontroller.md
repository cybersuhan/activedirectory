<h1>Creating Domain Controller with Windows Server 2019 in Virtualbox</h1>

<h2>Create a Virtual Machine</h2>
<p>I created a new VM and used following configuration:
<ul>
   <li>Name:</b> "DC</li>
   <li>Folder:</b> "<i>Selected a folder where the VM is to be saved</i>"</li>
   <li><b>ISO Image:</b> "<i>Selected the Server 2019 ISO image that I downloaded</i>"</li>
   <li><b>Base memory:</b> "2048 MB"</li>
   <li><b>Processors:</b> "2"</li>
   <li><b>Virtual Hard Disk:</b> "Create New, 50.00 GB"</li>
</ul>
<img src="https://i.imgur.com/b1tGPRd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/EJRoi1V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/HwDImLc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/jNEyOm2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<h2>Network Settings</h2>
<p>
I go to VM Settings -> Network and make the following changes:
   <ul>
      <li>Adapter 1:</b> Enable Network Adapter, <b>Attached to: </b>NAT</li>
      <li>Adapter 2:</b> Enable Network Adapter, <b>Attached to: </b>Internal Network</li>
   </ul>
</p>

<h2>Install Windows Server 2019</h2>
<p>After starting the DC VM in VirtualBox, I take the following steps to install Windows Server 2019: 
<ol>
   <li><b>Language:</b> "English" -> <i>Next</i></li>
   <li><b>OS to install: </b>Windows Server 2019 Standard Evaluation (Desktop Experience) -> <i>Next</i></li>
   <li><b>Type of Installation: </b>"Custom" -> <i>Next</i></li>
   <li>Allocate the only unallocated space -> <i>Next</i></li>
   <li><b>Administrator Password:</b> "CyberSuhanLab123" -> <i>Finish</i></li>
</ol>
<img src="https://i.imgur.com/dAARK98.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/zWqN3BF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/NeAaJxC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/bf2YqTZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/IAYYZwy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/ZnwZ1YB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>
<p><b>After Installation, I login to the Server using the password that I created earlier. I rename the PC to "DC".</b></p>


<h2>Set Up Network Names</h2>
<p>As I configured before, the Windows server VM has 2 network adapters connected to it. When I go to the Network Adapter settings, I can see both of the network adapters.
<img src="https://i.imgur.com/YjNfYul.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>   

<p>
I find the one that is connected to the internet. This is the NAT network. I change the name of the adapter to <code>INTERNET</code></p>
<p>The other adapter is meant to be the Internal Network Adapter. I change it's name to <code>INTERNAL</code>.
<img src="https://i.imgur.com/up9smQ4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<p>
After changing the names, I assign an IP address to the "INTERNAL" network. To do that, I take the following steps:
   <ol>
      <li>Right-Click the "Internal" Adapter and click "Properties"</li>
      <li>Double-Click on IPv4 (Internet Protocol Version 4 TCP/IPV4)</li>
      <li>Turn on "Use the following IP adress:"
         <ul>
            <li><b>IP address:</b> "172.16.0.1"</li>
            <li><b>Subnet mask:</b> "255.255.255.0"</li>
         </ul>
      </li>
      <li>For the DNS server address, I enter the loopback address:
         <ul>
            <li><b>Preferred DNS server:</b> "127.0.0.1"</li>
         </ul>
      </li>
      <li>I press OK to save the configuration.</li>
   </ol>
<img src="https://i.imgur.com/WMKVvrk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/46heXyg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
</p>
