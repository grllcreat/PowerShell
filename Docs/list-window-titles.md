## The *list-window-titles.ps1* Script

This PowerShell script list all main window titles and displays them in a table.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/list-window-titles.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./list-window-titles

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Lists window titles
.DESCRIPTION
	This PowerShell script list all main window titles and displays them in a table.
.EXAMPLE
	PS> ./list-window-titles
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

try {
	Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id,Name,mainWindowtitle -AutoSize
	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of list-window-titles.ps1*
