## The uninstall-visual-studio-code.ps1 PowerShell Script

This PowerShell script uninstalls Visual Studio Code from the local computer.

## Parameters
```powershell
uninstall-visual-studio-code.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./uninstall-visual-studio-code

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
<#
.SYNOPSIS
	Uninstalls Visual Studio Code
.DESCRIPTION
	This PowerShell script uninstalls Visual Studio Code from the local computer.
.EXAMPLE
	PS> ./uninstall-visual-studio-code
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

try {
	"Uninstalling Visual Studio Code, please wait..."

	& winget uninstall "Visual Studio Code"
	if ($lastExitCode -ne "0") { throw "Can't uninstall Visual Studio Code, is it installed?" }

	"Visual Studio Code is uninstalled now."
	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}

*Generated by convert-ps2md.ps1 using the comment-based help of uninstall-visual-studio-code.ps1*