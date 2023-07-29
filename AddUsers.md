<h1>Add Users in Domain using PowerShell script</h1>
<p>To replicate a small organization domain structure, I want to add 50 users to the domain for this lab. </p>

<h2>Generate User Names with GenerateData</h2>
<p>To create random user names, I use online data generator at https://generatedata.com/generator. Here are the steps to generate User names:
<ol>
  <li>Goto generatedata.com/generator</li>
  <li>I configure the data type and options:
    <ul>
      <li>Data Type: Names</li>
      <li>Examples: Alex Smith</li>
      <li>Options: Name Surname</li>
    </ul>
  <li>Click Generate</li>
  <li>Generate <b>50</b> rows -> <i>Generate</i></li>
  <li>Download</li>
  <li>In my desktop, I create a new folder and name it AD_PowershellScript. I download the file with the name "Names.csv". </li>
  <li>I right-click the downloaded file and click <b>Edit</b>. The generated file has the text "name" on top. I delete it so that the file starts with the generated names. I save the file again as <b>usernames.txt</b></li>
</ol>
  <img src="https://i.imgur.com/lZgY3PO.png" height="80%" width="80%" alt="Data Generator"/><br />
  <img src="https://i.imgur.com/5p5eSQG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/MDLZ5x6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/Pc3gQTA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/pUZ30Eh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <img src="https://i.imgur.com/SKIUPp4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<p><b>The name data is generated and is ready to use in powershell script at this point.</b></p>

<h2>PowerShell Script to Add Users</h2>
<p>I create a new powershell script file and save it in the same directory as usernames.txt file with the name <b>AddUsers.ps1</b>
<img src="https://i.imgur.com/xQh9Ql7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>Below is the powershell code that I used for adding the users:<br />
<code>
$password = ConvertTo-SecureString "UserPassword" -AsPlainText -Force
New-ADOrganizationalUnit -Name _USERS -ProtectedFromAccidentalDeletion $false
</code>
<code>
foreach ($n in Get-Content .\usernames.txt) {
    $first = $n.Split(" ")[0].ToLower()
    $last = $n.Split(" ")[1].ToLower()
    $username = "$($first.Substring(0,1))$($last)".ToLower()
    Write-Host "Creating user: $($username)" -BackgroundColor Black -ForegroundColor yellow
</code>
<code>
    New-AdUser -AccountPassword $password `
               -GivenName $first `
               -Surname $last `
               -DisplayName $username `
               -Name $username `
               -EmployeeID $username `
               -PasswordNeverExpires $true `
               -Path "ou=_USERS,$(([ADSI]`"").distinguishedName)" `
               -Enabled $true
}
</code>
</p>
<h3>Code Breakdown:</h3>
<p><code>$password = ConvertTo-SecureString "UserPassword" -AsPlainText -Force</code><br />
This line is creating a secure string $password by converting the plain text "UserPassword" to a secure format. This secure string is used later to set the password for each user created.</p>
<p><code>New-ADOrganizationalUnit -Name _USERS -ProtectedFromAccidentalDeletion $false</code><br />
This line is creating a new Active Directory Organizational Unit (OU) named <code>"_USERS"</code>. The <code>-ProtectedFromAccidentalDeletion $false</code> parameter ensures that accidental deletion of this OU is not protected, meaning it can be deleted without an additional confirmation prompt.
</p>
<p><code>foreach ($n in Get-Content .\usernames.txt) { ... }</code><br />
This line starts a loop that iterates through each line in the "usernames.txt" file.</p>
<p><code>$first = $n.Split(" ")[0].ToLower()</code><br />
This line splits the current line (name) by spaces and takes the first part, which is the first name of the user. The <code>ToLower()</code> function is used to convert the first name to lowercase.</p>
<p><code>$last = $n.Split(" ")[1].ToLower()</code><br />
This line is similar to the previous one but takes the second part of the current line, which is the last name of the user, and converts it to lowercase.</p>
<p><code>$username = "$($first.Substring(0,1))$($last)".ToLower()</code><br />
This line creates the username for the user by taking the first character of the first name and concatenating it with the last name. The resulting username is converted to lowercase and stored in the $username variable.</p>
<p><code>Write-Host "Creating user: $($username)" -BackgroundColor Black -ForegroundColor yellow</code><br />
This line simply displays a message indicating that a user is being created, and it shows the username in yellow text on a black background.</p>
<p><code>New-AdUser -AccountPassword $password ...</code><br />
This line creates a new Active Directory user using the New-AdUser cmdlet. It sets various properties for the user, including:
<ul>
  <li><code>-AccountPassword $password</code>: Sets the user's password to the previously created secure string $password.</li>
  <li><code>-GivenName $first</code>: Sets the given name (first name) of the user.</li>
  <li><code>-Surname $last</code>: Sets the surname (last name) of the user.</li>
  <li><code>-DisplayName $username</code>: Sets the display name of the user to be the same as the username.</li>
  <li><code>-Name $username</code>: Sets the name of the user to be the same as the username.</li>
  <li><code>-EmployeeID $username</code>: Sets the employee ID of the user to be the same as the username.</li>
  <li><code>-PasswordNeverExpires $true</code>: Ensures that the user's password never expires.</li>
  <li><code>-Path "ou=_USERS,$(([ADSI]"").distinguishedName)"</code>: Specifies the OU where the user will be created. It uses the previously created "_USERS" OU.</li>
  <li><code>-Enabled $true</code>: Enables the user account.</li>
  
  
</ul>
</p>
