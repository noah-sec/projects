<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Automated Implementation of STIG WN10-AC-000005</h1>

<!-- INTRODUCTION -->
<p align=center><i>"Windows 10 account lockout duration must be configured to 15 minutes or greater." <br>- STIG ID: WN10-AC-000005</i></p>

<hr><br>

<!-- IMPLEMENTATION -->
<h3><b>Business Impact:</b></h3>

<p>
"The account lockout feature, when enabled, prevents brute-force password attacks on the system. This parameter specifies the amount of time that an account will remain locked after the specified number of failed logon attempts." - STIG ID: WN10-AC-000005
</p><br>


<!-- IMPLEMENTATION -->
<h3><b>Technical Implementation:</b></h3>

<p>
1. Scanned Windows 10 Azure VM with Tenable Nessus using DISA STIG compliance audit policy.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-scan.png">
2. Exported scan results to an <a href="https://github.com/noah-sec/projects/blob/main/assets/stig-report.pdf">audit report</a>.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-report.png">
3. Examined the <a href="https://stigaview.com/products/win10/v3r1/WN10-AC-000005/">steps</a> to remediate vulnerability WN10-AC-000005.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig9.png">
4. Developed a <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig9.ps1">PowerShell script</a> to automatically implement the STIG fix.<br>
  
```powershell
#Requires -RunAsAdministrator
net accounts /lockoutduration:15
```
<br>
5. Ran the script and tested that the STIG fix was implemented.
</p><br>

<!-- TESTING 
### Testing and Validation-->

<!-- LESSONS 
### Lessons Learned-->

<!-- IMPROVEMENTS 
### Future Improvements-->

<!-- REFERENCES -->
<h3><b>References:</b></h3>

<p>Project code: <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig9.ps1">stig9.ps1</a></p>
<p>This project was completed as part of an internship as a Cybersecurity Support Engineer.</p><br>

<hr>

<div align=center><a href="https://github.com/noah-sec/projects/blob/main/vuln.md">Return to STIG project activities</a></div><br>
<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>

<!-- ANIMATED BOTTOM BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=footer" alt="footer"/>
