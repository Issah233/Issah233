<#
.SYNOPSIS
    These PowerShell scripts ensure that Windows is properly auditing “Other Object Access Events” and that advanced audit policies are enforced correctly.
.NOTES
    Author          : Issah Alhassan 
    LinkedIn        : www.linkedin.com/in/issah-alhassan 
    GitHub          : https://github.com/Issah233
    Date Created    : 2026-05-26
    Last Modified   : 2026-05-26
    Version         : 1.0
    CVEs            : N/A
    Plugin IDs      : N/A
    STIG-ID         : WN11-AU-000083 
    Documentation   : https://stigaview.com/products/win11/v2r7/WN11-AU-000083/

.TESTED ON
    Date(s) Tested  : 2026-05-26
    Tested By       : Issah Alhassan
    Systems Tested  : 
    PowerShell Ver. : 

.USAGE
    Put any usage instructions here.
    Example syntax:
    PS C:\> .\__remediation_template(STIG-ID- WN11-AU-000083 ).ps4
#>


# Run as Administrator

# Enable success auditing for Other Object Access Events
auditpol /set /subcategory:"Other Object Access Events" /success:enable

# Verify the setting
auditpol /get /subcategory:"Other Object Access Events"figured."

# Advanced audit policy override enabled
$RegistryPath = "HKLM:\SYSTEM\CurrentControlSet\Control\Lsa"

New-ItemProperty `
    -Path $RegistryPath `
    -Name "SCENoApplyLegacyAuditPolicy" `
    -Value 1 `
    -PropertyType DWord `
    -Force | Out-Null

Write-Host "Advanced audit policy override enabled."
