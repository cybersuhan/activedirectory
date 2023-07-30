<h1>Configuring Windows 10 Client</h1>
<p>In this part of the Lab, I configure the Windows 10 Client to use suhancyberlab.com domain so that any user listed in the Active Directory can use this client computer to login and use the machine.</p>

<h2>Set Client Name and Workgroup</h2>
<p>To set the client name and workgroup, I take the following steps:
<ol>
  <li>Right-Click Start menu-> System</li>
  <li>Click <b>Rename this PC (advanced)</b></li>
  <li>In the System properties window, Click <b>Change</b></li>
  <li>I rename the Computer to <b>CLIENT1</b>, according to the network map</li>
  <li>Click on <b>Domain</b> under the <i>Member of</i> section</li>
  <li>I enter the domain as <code>suhancyberlab</code></li>
  <li>Enter a username and password listed in the Active Directory. I used <b>a-suhanb</b> that I created earlier</li>
  <li>After successful logon, A notification pops up confirming the login</li>
</ol>

  <img src="https://i.imgur.com/H0CxSnx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/5zYQzoq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/6po1MBP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/XS03Mnr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/gfiQYhx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/89lPiw9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<h2>Logging in to the Created Domain from Client</h2>

<p>Since the Client Windows 10 is connected to the Domain Controller, I can now login as any user that is listed in the Directory. I just choose <b>Other user</b> at the logon screen. The Client Windows 10 lets me see the domain that I am signing into:<br />

  <img src="https://i.imgur.com/o3GJCfF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<p>At this point, Active Directory is setup on Domain Controller server, Client Windows is using the domain created in Domain Controller and The network infrastructure is working as the network map.</p>
