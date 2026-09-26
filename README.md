<h1>PowerShell Scripting Lab</h1>

<h2>Description</h2>
This project documents the development and execution of a production-ready PowerShell automation script designed to handle the secure offboarding of a departing employee. The script takes an active user identity and automates an immediate multi-step lockdown: disabling the account, randomizing the password, stripping all security groups, migrating the object to a restricted Organizational Unit (OU), and creating a compressed archive of their local profile data. Every action is outputted to a centralized compliance audit log.This lab demonstrates foundational system administration capabilities in scripting logic, enterprise security enforcement, lifecycle management, and administrative change-auditing.
<br />


<h2>Utilities Used</h2>

- <b>Windows PowerShell (Active Directory Module)</b> 
- <b>Active Directory Users and Computers</b>
- <b>File system Cmdlets (Compress-Archive, Out-File)</b>

<h2>Environments Used </h2>

- <b>Windows Server 2022</b>
- <b>Active Directory Domain: corp.local</b>

<h2>Program walk-through:</h2>

<p align="center">
1. Created the folder paths where the script, the archive files, and the compliance log trail will live. Created folders named "C:\AD-Cleanup" and "C:\OffboardingArchive". <br/>
<img src="https://github.com/user-attachments/assets/e8d19c48-3156-4165-91dc-355f84ae7746" height="80%" width="80%" alt="DiskSpaceReport.ps1"/>
<br />
<br />
2. Created new user to use as a test subject. Created user "Test Employee", and added them as a member of two security groups. <br/>
<img src="https://github.com/user-attachments/assets/79e1a066-84c5-4a19-8c2a-409a49dcf626" height="80%" width="80%" alt="DiskReport.csv"/>
<br />
<br />
3. In order to safely isolate offboarded accounts without deleting them immediately, I created a dedicated landing spot at the root of the domain. Created the following new OU: Stale Objects.  <br/>
<img src="https://github.com/user-attachments/assets/1edd89fc-9410-42d7-9e91-554f85acb76a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4. To prove the script can handle data lifecycle management. I simulated a user profile directory that needs to be backed up before the workstation gets wiped. Created the following folder: C:\Users\temployee. Inside it, I created two text files. <br/>
<img src="https://github.com/user-attachments/assets/319775d1-d427-49bc-b955-d4fa00e52bac" height="80%" width="80%" alt="SysemReport.ps1 Output"/>
<br />
<br />
5. Opened PowerShell ISE and wrote the following script into a new file saved as "C:\AD-Cleanup\Invoke-UserOffboarding.ps1".  <br/>
<img src="https://github.com/user-attachments/assets/be9bd4bd-c363-4d52-97d2-7175a3ffa61e" height="80%" width="80%" alt="SystemReport.txt"/>
<br />
<br />
6. Changed the directory to the cleanup folder and ran the script, targeting the test account.  <br/>
<img src="https://github.com/user-attachments/assets/be9bd4bd-c363-4d52-97d2-7175a3ffa61e" height="80%" width="80%" alt="SystemReport.txt"/>
<br />
<br />
7. Opened Active Directory Users and Computers to confirm the script worked.  <br/>
<img src="https://github.com/user-attachments/assets/fe72c918-54d3-4c46-bc9b-5faf0938010c" height="80%" width="80%" alt="StaleAccounts.csv"/>
<br />
<br />
8. Opened the OffboardingArchive folder to confirm there is a compressed file named "temployee_Profile_Archive.zip". finally, I opened the Offboarding_Compliance_Log.txt file to confirm the logs are tracked. <br/>
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
