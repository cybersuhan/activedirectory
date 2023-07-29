<h1>Creating a Domain</h1>

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
