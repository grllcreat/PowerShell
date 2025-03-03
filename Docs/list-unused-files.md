## The *list-unused-files.ps1* Script

This PowerShell script scans and lists files in a folder with last access time older than number of days.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/list-unused-files.ps1 [[-DirTree] <String>] [[-Days] <Int32>] [<CommonParameters>]

-DirTree <String>
    Specifies the path to the directory tree
    
    Required?                    false
    Position?                    1
    Default value                
    Accept pipeline input?       false
    Accept wildcard characters?  false

-Days <Int32>
    Specifies the number of days
    
    Required?                    false
    Position?                    2
    Default value                100
    Accept pipeline input?       false
    Accept wildcard characters?  false

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./list-unused-files C:\ 100

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Lists unused files in a directory tree
.DESCRIPTION
	This PowerShell script scans and lists files in a folder with last access time older than number of days.
.PARAMETER DirTree
	Specifies the path to the directory tree
.PARAMETER Days
	Specifies the number of days
.EXAMPLE
	PS> ./list-unused-files C:\ 100
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

param([string]$DirTree = "", [int]$Days = 100)

write-host "Listing files in $DirTree with last access time older than $Days days"

try {
	$cutOffDate = (Get-Date).AddDays(-$Days)

	Get-ChildItem -path $DirTree -recurse | Where-Object {$_.LastAccessTime -le $cutOffDate} | select fullname

	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of list-unused-files.ps1*
