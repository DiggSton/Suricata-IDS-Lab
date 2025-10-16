RDP
# Run as Administrator in PowerShell
Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name fDenyTSConnections -Value 0
Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
Write-Output "RDP enabled and firewall rule set."
//

SSH(Setup)
<#
Manual/OpenSSH installation steps if Windows Update is available:
1. Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
2. Start-Service sshd
3. Set-Service -Name sshd -StartupType Automatic
4. New-NetFirewallRule -Name "Allow-SSH" -DisplayName "Allow SSH" -Direction Inbound -Protocol TCP -LocalPort 22 -Action Allow
#>
//

# Run as Administrator
$Username = "testuser"
$Password = "Password123!"
net user $Username $Password /add
#testuser was a disposable account to generate logs for lab
//

# Windows Victim Notes

- Use PowerShell as Admin to run the scripts.
- If Add-WindowsCapability fails due to lack of Windows Update access, use manual Win32-OpenSSH package and follow instructions in docs.
- For RDP-based tests, make sure the Windows VM allows remote connections and the firewall rule is active.

