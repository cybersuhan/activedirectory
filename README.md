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
<p>The following are the steps I took chronologically to complete this lab project with direct links:
<ol>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/domaincontroller.md">Create a Windows Server Domain Controller in Virtual Box </a></li>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/creatingDomain.md">Create a Domain within the Domain Controller</a></li>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/RAS_NAT_installation.md">Configure RAT / NAS in the Domain Controller</a></li>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/DHCP_setup.md">Set up a DHCP Server in the Domain Controller</a></li>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/AddUsers.md">Add multiple dummy users in the Active Directory using Powershell</a></li>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/Windows10ClientInstallation.md">Create a Windows 10 Client</a></li>
 <li><a href="https://github.com/cybersuhan/activedirectory/blob/main/ClientConfiguration.md">Configure Client Windows to use the previously created domain</a></li>
</ol>
</p>

<!-- <h2>Oracle VirtualBox Appliance</h2>
<p>The VirtualBox Appliance for both, Domain Controller and Client1, are available for download from my google cloud drive.</p>
<p><a href="#">Download Appliances</a></p> -->













<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
