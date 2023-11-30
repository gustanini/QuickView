# QuickView

QuickViewAD is a PowerShell script designed to simplify and enhance Active Directory enumeration. It provides a streamlined approach to gather crucial information about users, computers, groups, domains, trusts, shares, and more within your Active Directory environment.

## Features

- **User Enumeration:** Retrieves details about all users, users with Service Principal Names (SPNs), and admin users.

- **Computer Enumeration:** Gathers information about all computer names, accessible computers using ICMP, and domain controllers.

- **Group Enumeration:** Gathers details about group names and SIDs, admin groups, domain admins group members, and enterprise admins.

- **Domain Enumeration:** Gathers information about the current domain, including infrastructure details, linked group policy objects, child domains, and more.

- **Trust Enumeration:** Gathers forest information, domains in the current forest, global catalogs, current domain trusts, and current forest trusts.

- **Shares Enumeration:** Gathers shares across all computers within the current Active Directory domain.

## Usage

1. Ensure you have the Active Directory PowerShell module installed.

2. Run the script in a PowerShell environment.

3. Follow the on-screen prompts to choose the enumeration options (use `get-help` to view available functions).

## Quick Start

1. Clone this repository:

```bash
git clone https://github.com/gustanini/QuickView.git
```

2. Navigate to the QuickView directory:

```bash
cd QuickView
```

3. Import the script:

```powershell
Import-Module .\QuickViewAD.ps1
```

4. Run all functions for quick enumeration (can also run individual functions, use `get-help` for more):

```powershell
Invoke-AllEnum
```

## Contributing

Contributions are welcome! If you have suggestions, improvements, or new features, feel free to open an issue or submit a pull request.

## Follow Us

[Hacker Hermanos](https://linktr.ee/hackerhermanos)

**Note**: This is by no means an exhaustive enumeration, you will also need to enumerate GPOs, OUs, ACLs. This script was made to run on new forests that you just compromised for achieving situational awareness.