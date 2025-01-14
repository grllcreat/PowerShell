## The *check-windows-system-files.ps1* Script

This PowerShell script checks the validity of the Windows system files. It requires admin rights.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/check-windows-system-files.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./check-windows-system-files
✔️ checked Windows system files

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Checks the validity of the Windows system files (requires admin rights)
.DESCRIPTION
	This PowerShell script checks the validity of the Windows system files. It requires admin rights.
.EXAMPLE
	PS> ./check-windows-system-files
	✔️ checked Windows system files
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

#Requires -RunAsAdministrator

try {
	sfc /verifyOnly
	if ($lastExitCode -ne "0") { throw "'sfc /verifyOnly' failed" }

	"✔️ checked Windows system files"
	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of check-windows-system-files.ps1*
