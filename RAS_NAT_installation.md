<h1>Installing RAS/NAT in Domain Controller Server</h1>

RAS stands for Remote Access Server and NAT stands for Network Access Translation. The purpose of RAS / NAT is when I add the Client Computers, the RAS / NAT allows the client to be on the internal network and but still be able to access the internet through the Domain Controller Server. The following graphic shows how the Clients will get internet access through Domain Controller:<br />

<img src="https://i.imgur.com/v9qIkBj.png" /><br />

<h2>Adding RAT / NAS Feature</h2>
To add RAT/NAS feature in the domain controller, I take the following steps:<br />
1. Open the <b>Server Manager</b>. Click on <b>Add roles and features</b><br />
2. Select "Role-based or feature based installation" -> Next<br />
3. Select the "DC.suhancyberlab" server -> Next<br />
4. Check the "<b>Remote Access</b>" option -> Next<br />
5. In the Role Services, Check on Routing. A new window will popup. I click on "<b>Add Features</b><br />. The Direct Access and VPN (RAS) and Routing should be checked. -> Next<br />
6. Keep the Role Services to default -> Next<br />
7. Click <b>Install</b><br />

