<h1>Setting up DHCP Server in Domain Controller</h1>
<p>The next thing I do is setup a DHCP server in the Domain Controller Server. The domain controller will allow the clients to get an IP address which will enable them to connect to the internet even though they are on the private internal network.</p>

<h2>Install DHCP</h2>
<p>To Install DHCP, I take the following steps:</p>
<p>
  <ol>
    <li>Open Server Manager and click on <b>Add roles and features</b></li>
    <li>Select "<b>Role-based or feature-based installation</b>" -> <i>Next</i></li>
    <li>Select the "DC.suhancyberlab" server -> <i>Next</i></li>
    <li>Check the <b>DHCP Server</b> checkbox, Click on <b>Add Feature</b>, -> <i>Next</i></li>
    <li>Keep the Features to default -> <i>Next</i></li>
    <li>Click Install</li>
  </ol>

  <img src="https://i.imgur.com/eoUuKIE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/2sgVRDf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/6t0LOhv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/gQIHjYH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/NK4Q1yR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/T4SamfA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
</p>

<h2>Configure DHCP</h2>
<p>After the installation, I need to configure DHCP. According to the Network Map, I need to set up DHCP so that the clients can get an IP address within the 172.16.0.100-200 range automatically. To do that, I take the following steps:</p>
<p>
<ol>
  <li>In the Server Manager, Click Tools -> DHCP</li>
  <li>Click Dropdown button in the "dc.suhancyberlab.com -> Right-Click on IPv4 -> New Scope</li>
  <li>I find it easier to name the Scope according to the IP address range. So, I name the Scope "172.16.0.100-200" -><i>Next</i></li>
  <li>I put the following information in the IP Address Range window
    <ul>
      <li><b>Start IP Address:</b> "172.16.0.100"</li>
      <li><b>End IP Address:</b> "172.16.0.200"</li>
      <li><b>Length:</b> "24"</li>
      <li><b>Subnet Mask:</b> "255.255.255.0"</li>
    </ul>
    -> <i>Next</i>
  </li>
  <li>I dont want any exclusions so I leave the exclusions to default. </li>
  <li>Lease duration is how long a client can use an IP address before it gets refreshed. For this lab, I leave it to 8 Days. -> <i>Next</i></li>
  <li>In the Configure DHCP Options, I select <b>Yes, I want to configure these options now</b> -> <i>Next</i></li>
  <li>For the Default gateway, I use the address 172.16.0.1 -> <i>Next</i></li>
  <li>In the Domain Name and DNS Service Window, I make sure that the Parent Domain is <b>suhancyberlab.com</b> -> <i>Next</i></li>
  <li>For the WINS, I leave it as it is. -> <i>Next</i></li>
  <li>I select <b>Yes, I want to activate this scope now</b> -> <i>Next</i></li>
  <li>Click Finish</li>
  <li>In the DHCP window, I Right-Click the <b>dc.suhancyberlav=b.com and click authorize. </b> </li>
</ol>

  <img src="https://i.imgur.com/rBZuwgn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/Zlg72dt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/25VdfUz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/mCsGuL2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/L9yz7rC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/lMiOauj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/LDJxbeO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/NGvQytI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/dUJ4Lxa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/9XRKsh3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/i9wp9Zn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br /><br />
  
</p>

<p><b><i>At this point, the DHCP Server is installed and configured in the Domain Controller Server</i></b></p>
