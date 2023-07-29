<h1>Installing RAS/NAT in Domain Controller Server</h1>

RAS stands for Remote Access Server and NAT stands for Network Access Translation. The purpose of RAS / NAT is when I add the Client Computers, the RAS / NAT allows the client to be on the internal network and but still be able to access the internet through the Domain Controller Server. The following graphic shows how the Clients will get internet access through Domain Controller:<br />

<img src="https://i.imgur.com/v9qIkBj.png" /><br />

<h2>Adding Routing Feature</h2>
To add RAT/NAS feature in the domain controller, I take the following steps:<br />
1. Open the <b>Server Manager</b>. Click on <b>Add roles and features</b><br />
2. Select "Role-based or feature based installation" -> Next<br />
3. Select the "DC.suhancyberlab" server -> Next<br />
4. Check the "<b>Remote Access</b>" option -> Next<br />
5. In the Role Services, Check on Routing. A new window will popup. I click on "<b>Add Features</b><br />. The Direct Access and VPN (RAS) and Routing should be checked. -> Next<br />
6. Keep the Role Services to default -> Next<br />
7. Click <b>Install</b><br />
<img src="https://i.imgur.com/REAHlTS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/CT6Z0pr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/bUUdCIa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/K9wjE4W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/cFj1nm8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/SJNklED.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />

<h2>Remote Access Configuration</h2>
After the installation, I configure the Routing by taking the following steps:<br />

1. Click on Tools -> Routing and Remote Access
2. Right click on "DC (local)" -> "Configure and Enable Routing and Remote Access.<br />
3. The Routing and Remote Access Server Setup Wizard opens. I click on <b>Next</b><br />
4. I select <b>Network address Translation (NAT)</b>. This will allow clients to connect to the Internet using the Server's IP Address.<br />
5. In the NAT Internet connection page, I <b><i>choose the interface that DC uses to connect to the Internet</i></b> -> Next<br />
6. I click Finish to complete the configuration of NAT.<br />
7. In the Routing and Remote Access Window, the DC (local) information page confirms that Routing and Remote Access is configured on the server.<br />

<img src="https://i.imgur.com/uzGnmFB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/WnyqV9O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/7YvbNrm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/6BTR8KO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />


<b>At this point, the RAS/NAT is configured in the Domain Controller Server</b>
