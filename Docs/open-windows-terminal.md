## The *open-windows-terminal.ps1* Script

This script launches the Windows Terminal application.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/open-windows-terminal.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./open-windows-terminal

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Launches the Windows Terminal app
.DESCRIPTION
	This script launches the Windows Terminal application.
.EXAMPLE
	PS> ./open-windows-terminal
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

Start-Process wt.exe
exit 0 # success
```

*Generated by convert-ps2md.ps1 using the comment-based help of open-windows-terminal.ps1*
