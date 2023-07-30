<h1>Installing Client Machine in Virtualbox</h1>
<p>For this lab project, I chose Windows 10 as a client device. This VM replicates a workstation in a business environment.</p>

<h2>Installing Windows 10 in Virtualbox</h2>
<p>In Virtualbox, I create a new VM and Enter the following configuration:
<ul>
  <li><b>Name:</b> "Windows10Client"</li>
  <li><b>Folder:</b> "<i>Select folder where the VM will reside</i>"</li>
  <li><b>ISO Image:</b> "<i>Select the Windows 10 ISO Image file</i>"</li>
  <li><b>Base Memory:</b> "2048MB"</li>
  <li><b>Processors:</b> "1"</li>
  <li><b>Disk Size:</b> "50.00GB"</li>

<img src="https://i.imgur.com/SoZfJRo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/ZBXEHkT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/LNXlJDF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</ul>


</p>

<p>Before I start the machine, I set the VM's network settings to the following configuration:
<ul>
  <li><b>Adapter 1:</b> Enable Network Adapter, <b>Attached to</b>: Internal Network</li>
</ul>
<img src="https://i.imgur.com/52xIjzm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<p>
  Next, I start the VM to install Windows 10.<br />

<img src="https://i.imgur.com/NBodn45.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/QteVuHE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/quLjCtE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<p>During the installation, I select all the default settings. 
  <ul>
    <li>I set up the VM for personal use</li>
    <li>Instead of creating a microsoft account, I set up an Offline account. Then I click on <b>Limited Exxperience</b>.</li>
    <li>When Windows 10 asks me to create a user, I just create an account with the name "user" and no password</li>
    <li>I skip everything else and wait for the Windows to get ready</li>
  </ul>
<img src="https://i.imgur.com/p3PlyFW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/gC1XASn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/EuTVRCr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/68uMOIW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />  
  </p>

  <p>After the installation, I check the IP Address of the Machine by running <code>ipconfig</code> on command prompt. I see that the IPv4 address is <code>172.16.0.100</code> and the gateway is <code>172.16.0.1</code> as I configured in the Domain Controller.<br />
    <img src="https://i.imgur.com/SyTAwmM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  </p>

  <p>At this point, the Windows Client is installed, the DHCP is working in Domain Controller and the client is connected to the internet through the Domain Controller. </p>
  <p>For the final part of this lab, I will configure the Windows 10 Client to use the suhancyberlab.com domain so that any user in the Active Directory can login to this client.</p>
