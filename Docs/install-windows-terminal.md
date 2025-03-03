## The *install-windows-terminal.ps1* Script

This PowerShell script installs Windows Terminal from the Microsoft Store.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/install-windows-terminal.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./install-windows-terminal

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Installs Windows Terminal
.DESCRIPTION
	This PowerShell script installs Windows Terminal from the Microsoft Store.
.EXAMPLE
	PS> ./install-windows-terminal
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

try {
	"Installing Windows Terminal, please wait..."

	& winget install --id Microsoft.WindowsTerminal --accept-package-agreements --accept-source-agreements
	if ($lastExitCode -ne "0") { throw "'winget install' failed" }

	"Windows Terminal installed successfully."
	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of install-windows-terminal.ps1*
