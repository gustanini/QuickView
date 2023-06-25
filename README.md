# QuickView

QuickView is an automated enumeration tool inspired by winPEAS. It provides a fast and comprehensive way to gather information about the system, users, groups, policies, computers, sessions, SPNs, and shares. The script leverages PowerShell commands and the Powerview.ps1 module for performing various queries.

## Features

- Automated enumeration of system information, users, groups, policies, computers, sessions, SPNs, and shares.
- Blazing fast execution for quick enumeration.
- Supports optional thorough mode for additional queries (affects execution time).
- Color-coded output for easy readability.
- Saves output to a file for future reference.

### Commands Executed

- Get-NetDomain - Displays an overview of current Domain information.
- Get-NetUser - Filtered display of available users within the Domain.
- Get-NetGroup - Filtered display of available groups within the Domain.
- Invoke-EnumerateLocalAdmin - Displays which users are local administrators and in which computers.
- Net Accounts - Account policy information (password information).
- Get-NetComputer - Displays domain joined machines.
- Get-NetGPO - Displays Group Policy Objects.
- Get-NetComputer | Get-NetLoggedon - Displays users with cached credentials (locally and remotely if user is privileged enough).
- Get-NetComputer | Get-NetSession - Displays users with active sessions (locally and remotely if user is privileged enough).

Extra commands (use -thorough flag), these commands may or may not work, and they will usually impact execution time considerably:

- Invoke-UserHunter - finds machines on the local domain where specified users are logged into, and checks if the current user has local admin access to found machines.
- Find-LocalAdminAccess - finds machines on the domain that the current user has local admin access to
- Find-DomainShare - Searches for computer shares on the domain.

For more information visit the official [powersploit documentation](https://powersploit.readthedocs.io/en/stable/Recon/README/), [powersploit recon documentation 2](https://powersploit.readthedocs.io/en/latest/Recon/Find-DomainShare/).

## Prerequisites

- Windows operating system
- PowerShell version 3.0 or above
- Imported PowerView.ps1 module

## Usage

1. Clone or download the PowerShell script.
2. Ensure that the Powerview.ps1 module is available in the same directory as the script.
3. Open a PowerShell terminal.
4. Navigate to the directory where the script is located.
5. Run the script using the following command:

```powershell
.\EnumerationScript.ps1 [-Thorough] [-h | --help]
```

### Modes

The -Thorough flag can be used to enable additional queries (Find-LocalAdminAccess, Invoke-UserHunter, Find-DomainShare). Note that enabling thorough mode may increase execution time.

The -h or --help flag can be used to display the help message, providing information about the usage and available optional arguments.

## Output

QuickView will generate an output file named output.txt in the same directory as the script.
The output file will contain the results of the executed queries, each section labeled with the corresponding command name.

The command names will be displayed in green, and the output of each command will be displayed in yellow for easy identification.

## Disclaimer

This script is intended for educational and informational purposes only. Use this script responsibly and with proper authorization.

I am not responsible for any misuse or damage caused by this script.

## Credits

This script utilizes the Powerview.ps1 module by Will Schroeder (@harmj0y).
Powerview.ps1: https://github.com/PowerShellMafia/PowerSploit/blob/master/Recon/PowerView.ps1
