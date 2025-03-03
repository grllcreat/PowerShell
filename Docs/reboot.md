## The *reboot.ps1* Script

This PowerShell script reboots the local computer immediately (needs admin rights).

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/reboot.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./reboot

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Reboots the computer (needs admin rights)
.DESCRIPTION
	This PowerShell script reboots the local computer immediately (needs admin rights).
.EXAMPLE
	PS> ./reboot
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

#Requires -RunAsAdministrator

try {
	if ($IsLinux) {
		& sudo reboot
	} else {
		Restart-Computer
	}
	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of reboot.ps1*
