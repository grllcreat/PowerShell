## The *open-spotify.ps1* Script

This script launches the Spotify application.

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/open-spotify.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./open-spotify

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Launches the Spotify app
.DESCRIPTION
	This script launches the Spotify application.
.EXAMPLE
	PS> ./open-spotify
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

Start-Process spotify:
exit 0 # success
```

*Generated by convert-ps2md.ps1 using the comment-based help of open-spotify.ps1*
