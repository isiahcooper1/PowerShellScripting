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
<img src="https://github.com/user-attachments/assets/bd1ab74f-0941-4f5e-9a0e-f2497f00ca8d" height="80%" width="80%" alt="DiskSpaceReport.ps1"/>
<br />
<br />
2. Created new user to use as a test subject. Created user "Test Employee", and added them as a member of two security groups. <br/>
<img src="https://github.com/user-attachments/assets/7fbb8df5-ec62-4437-8ae3-5a7d8d0bda51" height="80%" width="80%" alt="DiskReport.csv"/>
<br />
<br />
3. In order to safely isolate offboarded accounts without deleting them immediately, I created a dedicated landing spot at the root of the domain. Created the following new OU: Stale Objects.  <br/>
<img src=https://github.com/user-attachments/assets/a138c0b1-7b83-46b5-b61a-59237fa0ff4e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4. To prove the script can handle data lifecycle management. I simulated a user profile directory that needs to be backed up before the workstation gets wiped. Created the following folder: C:\Users\temployee. Inside it, I created two text files. <br/>
<img src="https://github.com/user-attachments/assets/4f0236a2-0705-44c2-9a30-3c6aefed0718" height="80%" width="80%" alt="SysemReport.ps1 Output"/>
<br />
<br />
5. Opened PowerShell ISE and wrote the following script into a new file saved as "C:\AD-Cleanup\Invoke-UserOffboarding.ps1".  <br/>
<img src="https://github.com/user-attachments/assets/a682c29e-846a-4f59-861d-a228925e00e8" height="80%" width="80%" alt="SystemReport.txt"/>
<br />
<br />
6. Opened PowerShell, changed the directory to the cleanup folder and ran the script, targeting the test account.  <br/>
<img src="https://github.com/user-attachments/assets/f1e40565-9b74-4437-af54-7a2104fbb32f" height="80%" width="80%" alt="SystemReport.txt"/>
<br />
<br />
7. Opened Active Directory Users and Computers to confirm the script worked, and the user account is disabled and was moved to the Stale Objects OU.  <br/>
<img src="https://github.com/user-attachments/assets/9c90eeb9-b4f6-456f-9927-0c94355d429f" height="80%" width="80%" alt="StaleAccounts.csv"/>
<br />
<br />
8. Opened the OffboardingArchive folder to confirm there is a compressed file named "temployee_Profile_Archive.zip". Finally, I opened the Offboarding_Compliance_Log.txt file to confirm the logs are tracked. <br/>
<img src="https://github.com/user-attachments/assets/bfb5ede8-397b-438f-902f-b4f3577e70d0" height="80%" width="80%" alt="StaleAccounts.csv"/>
<br />
<img src="https://github.com/user-attachments/assets/9b1c9eac-b619-4958-8f6b-9aa93f49a4f9" height="80%" width="80%" alt="StaleAccounts.csv"/>
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
