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

</p>
<p>The name data is generated and is ready to use in powershell script at this point.</p>
