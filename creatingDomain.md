<h1>Creating a Domain</h1>

<p>Next step is to create an Active Directory Domain Name. To do this, I open the Server Manager and take the following steps:
<ol>
   <li>Click on <b>"Add roles and features"</b></li>
   <li>Select "Role based or feature-based installation" -> <i>Next</i></li>
   <li>Select Destination server -> <i>Next</i></li>
   <li>In Server roles, tick "Active Directory Domain Services", Click "Add Features" -> <i>Next</i></li>
   <li>In Features, keep default settings -> <i>Next</i></li>
   <li>Click <b>Install</b></li>
</ol>
<img src="https://i.imgur.com/peY3HtV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/C99RndX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/PHszii4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/6py1gvu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/tQ3a7w2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/nTjSCzK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/wZXIhAl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
</p>

<h2>Configuring Domain</h2>
<p>
After the installation, I need to work on the post-deployment configuration. To do this, I take the following steps:
   <ol>
      <li>Click on the Flag icon on the top right</li>
      <li>Turn on "Add a new forest" and for the root domain name, enter "suhancyberlabs.com" -> <i>Next</i></li>
      <li>In Domain Controller Options, I enter a password. (I dont use this password anywhere in this lab) -> <i>Next</i></li>
      <li>In DNS Options, I dont change anything, I just "click" Next on everything else and finally "Install" <i>Next</i></li>
   </ol>
</p>
<p>
After Installation, The VM restarts automatically. <br />
<img src="https://i.imgur.com/f6Vv20c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/yazW7X4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/jS6xwzt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
</p>
After the VM restarts, The Domain Name is shown before the Account Name:<br />
<img src="https://i.imgur.com/FWsZFf4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

<b>At this point, the domain is created and I can login to the domain.</b>
</p>

<h2>Creating Admin Account</h2>
<p>
It is a good practice to create a new admin account instead of using the built-in administrator account. To create the admin account, I take the following steps:<br />
</p>
<h3>Creating a new account</h3>
<p>
<ol>
   <li>Click on start -> Windows Administrative Tools -> Active Directory Users and Computers.</li>
   <li>Right-Click on the newly created domain -> New -> Organizational Unit.</li>
   <li>In the New Object - Organizational Unit window, I name the unit as "_ADMINS" and click OK.</li>
   <li>Right-Click "_ADMINS" -> New -> User</li>
   <li>In the New Object - User window I fill in the following Information:
      <ul>
         <li><b>First Name:</b> "Suhan"</li>
         <li><b>Last name:</b> "Budhathoki"</li>
         <li><b>User logon name:</b> "a-suhanb"</li>
      </ul>
      <i>I used the prefix "a-" before my logon name to indicate that this account is an administrator account. It is not necessary but I like to know which accounts are admin accounts whenever I browse through the users list.</i>
   </li>
   <li> I click next and set the password to "CyberLab123@" for this account.  I <b>uncheck</b> the "User must change password at next logon" and <b>check</b> "Password never expires".</li>
   <li>I click "Next" and review the New User information. Everything looks correct, so I click "Finish".</li>
</ol>

<img src="https://i.imgur.com/66iWAxe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/mx85IDA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/RiC19cM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/pMa5dfE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/3v2QIey.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/o8kgtYW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/vNIkQoK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<h3>Administrator Privilages to the Admin account</h3>
<p>
Now I have an account but it does not have administrator privilages yet. To add the administrative privilages, I take the following steps:
   <ol>
      <li>Right CLick on the created User account under "_ADMINS" -> Properties.</li>
      <li>On the user account properties, I click on the "Member Of" tab.</li>
      <li>In the Member of, I click Add to open the "Select Groups" window.</li>
      <li>In the "Object names I write "domain admins" and click on "Check Names". The AD resolves it to "<u>Domain Admins</u>". I click "OK".</li>
      <li>In the user properties, I click OK.</li>
   </ol>
<img src="https://i.imgur.com/1b7Calt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/gBqZMxM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/k47M4BV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/w7qciCy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/KLNfKTa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<p>
<b>The new administrator account is created and administrative privilages is given to the account. I sign out of the built-in administrator account to login to the server with this newly created admin account.</b>
<img src="https://i.imgur.com/0hYfL8T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

