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

After Installation, I login to the Server using the password that I created earlier. I rename the PC to "DC".
