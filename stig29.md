<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Automated Implementation of WN10-CC-000005</h1>

<!-- INTRODUCTION -->
<p align=center><i>"Camera access from the lock screen must be disabled." <br>- STIG ID: WN10-CC-000005</i></p>

<hr><br>

<!-- IMPLEMENTATION -->
<h3><b>Business Impact:</b></h3>

<p>
"Enabling camera access from the lock screen could allow for unauthorized use. Requiring logon will ensure the device is only used by authorized personnel." - STIG ID: WN10-CC-000005
</p><br>


<!-- IMPLEMENTATION -->
<h3><b>Technical Implementation:</b></h3>

<p>
1. Scanned Windows 10 Azure VM with Tenable Nessus using DISA STIG compliance audit policy.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-scan.png">
2. Exported scan results to an <a href="https://github.com/noah-sec/projects/blob/main/assets/stig-report.pdf">audit report</a>.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-report.png">
3. Examined the <a href="https://stigaview.com/products/win10/v3r1/WN10-CC-000005/">steps</a> to remediate vulnerability WN10-CC-000005.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig29.png">
4. Developed a <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig29.ps1">PowerShell script</a> to automatically implement the STIG fix.<br>
  
```powershell
#Requires -RunAsAdministrator
# Defining the registry path and registry value:
$registryPath = "HKLM:\SOFTWARE\Policies\Microsoft\Windows\Personalization\"
$valueName = "NoLockScreenCamera"
$valueData = 1

# Checking for registry path, if none then creating path:
if (-not (Test-Path $registryPath)) {
    Write-Host "Registry path '$registryPath' not found. Creating it now."
    New-Item -Path $registryPath -Force
} else {
    Write-Host "Registry path '$registryPath' already exists."
}

# Setting value:
Set-ItemProperty -Path $registryPath -Name $valueName -Value $valueData -Type DWord

# Setting output message:
Write-Host "Registry value '$valueName' set to '$valueData' at '$registryPath'."
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

<p>Project code: <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig29.ps1">stig29.ps1</a></p>
<p>This project was completed as part of an internship as a Cybersecurity Support Engineer.</p><br>

<hr>

<div align=center><a href="https://github.com/noah-sec/projects/blob/main/vuln.md">Return to STIG project activities</a></div><br>
<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>

<!-- ANIMATED BOTTOM BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=footer" alt="footer"/>
