## The *cd-music.ps1* Script

This PowerShell script changes the working directory to the user's music folder.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/cd-music.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./cd-music
📂/home/Markus/Music

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Sets the working directory to the user's music folder
.DESCRIPTION
	This PowerShell script changes the working directory to the user's music folder.
.EXAMPLE
	PS> ./cd-music
	📂/home/Markus/Music
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

try {
	if ($IsLinux) {
		$Path = Resolve-Path "~/Music"
	} else {
		$Path = [Environment]::GetFolderPath('MyMusic')
	}
	if (Test-Path "$Path" -pathType container) {
		Set-Location "$Path"
		"📂$Path"
		exit 0 # success
	}
	throw "User's music folder at 📂$Path doesn't exist (yet)"
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of cd-music.ps1*
