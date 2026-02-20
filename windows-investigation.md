# Windows Investigation - Key Findings

## Scheduled Tasks
- Check task name, execution time, and the exact command being executed
- Malicious tasks often run PowerShell or CMD with encoded commands
- Location: Task Scheduler > Task Scheduler Library

## User & Last Logon
- CMD: `net user <username>`
- PowerShell: `Get-LocalUser | Select Name, LastLogon`
- Look for logins at unusual hours or from unexpected accounts

## Registry Persistence
- Attackers modify registry to survive reboot
- Key location to check: `HKLM\Software\Microsoft\Windows\CurrentVersion\Run`
- Any unknown executable here is suspicious

## Host File Manipulation (DNS Poisoning)
- Location: `C:\Windows\System32\drivers\etc\hosts`
- Attackers add malicious entries to redirect legitimate domains
- Any entry pointing to unknown IPs is a red flag

## Firewall & Open Ports
- Check if sensitive ports are exposed publicly by cheking firewall inbound policy 
- Use: `netstat -an` to see active connections and listening ports
