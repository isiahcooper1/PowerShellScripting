<h1>PowerShell Scripting Lab</h1>

<h2>Description</h2>
A collection of PowerShell automation scripts built to simulate real sysadmin workflows including disk space monitoring, system inventory reporting, and Active Directory account auditing. Each script is self-contained, exports results to a structured output file, and is written with inline comments for readability and maintainability. These scripts reflect the shift from manual administration to repeatable, auditable automation.
<br />


<h2>Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Active Directory PowerShell Module (Get-ADUser)</b>
- <b>Get-CimInstance (hardware and OS data collection)</b>
- <b>Get-PSDrive (disk enumeration)</b>
- <b>Export-Csv (structured data output)</b>
- <b>Tee-Object (simultaneous console and file output)</b>

<h2>Environments Used </h2>

- <b>Windows Server 2022</b>
- <b>Microsoft Hyper-V — AD-Lab-Internal isolated virtual switch (carried over from Lab 1)</b>

<h2>Program walk-through:</h2>

<p align="center">
1. Get-DiskSpaceReport.ps1 open in VS Code alongside the PowerShell console output displaying all local drives with total, used, and free GB values and a status column flagging any drive below the defined 20GB threshold. <br/>
<img src="https://github.com/user-attachments/assets/e8d19c48-3156-4165-91dc-355f84ae7746" height="80%" width="80%" alt="DiskSpaceReport.ps1"/>
<br />
<br />
2. DiskReport.csv showing the structured output with all drive data captured in a format suitable for logging or ongoing monitoring. <br/>
<img src="https://github.com/user-attachments/assets/79e1a066-84c5-4a19-8c2a-409a49dcf626" height="80%" width="80%" alt="DiskReport.csv"/>
<br />
<br />
3. Get-SystemReport.ps1 open showing the modular section functions used to collect OS details, hardware specs, network adapter info, disk summary, and installed software.  <br/>
<img src="https://github.com/user-attachments/assets/1edd89fc-9410-42d7-9e91-554f85acb76a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4. Full system report printed to the PowerShell console with all sections populated with live machine data pulled from DC01.  <br/>
<img src="https://github.com/user-attachments/assets/319775d1-d427-49bc-b955-d4fa00e52bac" height="80%" width="80%" alt="SysemReport.ps1 Output"/>
<br />
<br />
5. SystemReport.txt open showing the formatted, section-divided report in a state ready to be filed, archived, or shared with a team.  <br/>
<img src="https://github.com/user-attachments/assets/be9bd4bd-c363-4d52-97d2-7175a3ffa61e" height="80%" width="80%" alt="SystemReport.txt"/>
<br />
<br />
6. Get-StaleAccounts.ps1 open in VS Code alongside the PowerShell console output displaying all flagged inactive accounts with their last logon date and calculated days inactive, queried directly from Active Directory.  <br/>
<img src="https://github.com/user-attachments/assets/be9bd4bd-c363-4d52-97d2-7175a3ffa61e" height="80%" width="80%" alt="SystemReport.txt"/>
<br />
<br />
7. StaleAccounts.csv showing the full audit results in a structured format reflecting the kind of output that would be reviewed during a security or compliance audit.  <br/>
<img src="https://github.com/user-attachments/assets/fe72c918-54d3-4c46-bc9b-5faf0938010c" height="80%" width="80%" alt="StaleAccounts.csv"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
