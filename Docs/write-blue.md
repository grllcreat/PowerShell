## The *write-blue.ps1* Script

This PowerShell script writes text in a blue foreground color.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/write-blue.ps1 [[-text] <String>] [<CommonParameters>]

-text <String>
    Specifies the text to write
    
    Required?                    false
    Position?                    1
    Default value                
    Accept pipeline input?       false
    Accept wildcard characters?  false

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./write-blue "Hello World"

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Writes text in a blue foreground color
.DESCRIPTION
	This PowerShell script writes text in a blue foreground color.
.PARAMETER text
	Specifies the text to write
.EXAMPLE
	PS> ./write-blue "Hello World"
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

param([string]$text = "")

if ($text -eq "" ) { $text = read-host "Enter the text to write" }

write-host -foregroundColor blue "$text"

exit 0 # success
```

*Generated by convert-ps2md.ps1 using the comment-based help of write-blue.ps1*
