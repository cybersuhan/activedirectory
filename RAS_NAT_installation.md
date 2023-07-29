<h1>Installing RAS/NAT in Domain Controller Server</h1>

<p>RAS stands for Remote Access Server and NAT stands for Network Access Translation. The purpose of RAS / NAT is when I add the Client Computers, the RAS / NAT allows the client to be on the internal network and but still be able to access the internet through the Domain Controller Server. The following graphic shows how the Clients will get internet access through Domain Controller:

<img src="https://i.imgur.com/v9qIkBj.png" /><br />
</p>

<h2>Adding Routing Feature</h2>

<p>
  To add RAT/NAS feature in the domain controller, I take the following steps:
  <ol>
    <li>Open the <b>Server Manager</b>. Click on <b>Add roles and features</b></li>
    <li>Select "Role-based or feature based installation" -> <i>Next</i></li>
    <li>Select the "DC.suhancyberlab" server -> <i>Next</i></li>
    <li>Check the "<b>Remote Access</b>" option -> <i>Next</i></li>
    <li>In the Role Services, Check on Routing. A new window will popup. I click on "<b>Add Features</b><br />. The Direct Access and VPN (RAS) and Routing should be checked. -> <i>Next</i></li>
    <li>Keep the Role Services to default -> <i>Next</i></li>
    <li>Click <b>Install</b></li>
  </ol>
<img src="https://i.imgur.com/REAHlTS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/CT6Z0pr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/bUUdCIa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/K9wjE4W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/cFj1nm8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/SJNklED.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>

<h2>Remote Access Configuration</h2>
<p>
After the installation, I configure the Routing by taking the following steps:
<ol>
  <li>Click on Tools -> Routing and Remote Access</li>
  <li>Right click on "DC (local)" -> "Configure and Enable Routing and Remote Access.</li>
  <li>The Routing and Remote Access Server Setup Wizard opens. -> <i>Next</i></li>
  <li>I select <b>Network address Translation (NAT)</b>. This will allow clients to connect to the Internet using the Server's IP Address.</li>
  <li>In the NAT Internet connection page, I <b><i>choose the interface that DC uses to connect to the Internet</i></b> -> <i>Next</i></li>
  <li>I click Finish to complete the configuration of NAT.</li>
  <li>In the Routing and Remote Access Window, the DC (local) information page confirms that Routing and Remote Access is configured on the server.</li>
</ol>

<img src="https://i.imgur.com/uzGnmFB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/WnyqV9O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/7YvbNrm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<img src="https://i.imgur.com/6BTR8KO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
</p>


<p><b>At this point, the RAS/NAT is configured in the Domain Controller Server</b></p>
