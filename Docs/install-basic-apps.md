## The *install-basic-apps.ps1* Script

This PowerShell script installs basic Windows apps such as browser, e-mail client, etc.
Apps from Microsoft Store are preferred (due to security and automatic updates).

## Parameters
```powershell
/home/mf/Repos/PowerShell/Scripts/install-basic-apps.ps1 [<CommonParameters>]

[<CommonParameters>]
    This script supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS> ./install-basic-apps

```

## Notes
Author: Markus Fleschutz | License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

## Source Code
```powershell
<#
.SYNOPSIS
	Installs basic apps
.DESCRIPTION
	This PowerShell script installs basic Windows apps such as browser, e-mail client, etc.
	Apps from Microsoft Store are preferred (due to security and automatic updates). 
.EXAMPLE
	PS> ./install-basic-apps
.LINK
	https://github.com/fleschutz/PowerShell
.NOTES
	Author: Markus Fleschutz | License: CC0
#>

try {
	$StopWatch = [system.diagnostics.stopwatch]::startNew()

	Write-Host "⏳ (1/34) Loading Data/basic-apps.csv...    " -noNewline
	$Table = Import-CSV "$PSScriptRoot/../Data/basic-apps.csv"
	$NumEntries = $Table.count
	"$NumEntries apps"
	"⏳ (2/34) About to install or upgrade:"
	""
	foreach($Row in $Table) {
		[string]$AppName = $Row.APPLICATION
		Write-Host " · $AppName" -NoNewline
	}
	""
	""
	"Press <Control> <C> to abort, otherwise the installation will start in 15 seconds..."
	Start-Sleep -seconds 15

	[int]$Step = 3
	[int]$Failed = 0
	foreach($Row in $Table) {
		[string]$AppName = $Row.APPLICATION
		[string]$Category = $Row.CATEGORY
		[string]$AppID = $Row.APPID
		Write-Host " "
		Write-Host "⏳ ($Step/$($NumEntries + 2)) Installing $Category '$AppName'..."
		& winget install --id $AppID --accept-package-agreements --accept-source-agreements
        	if ($lastExitCode -ne "0") { $Failed++ }
		$Step++
	}
	[int]$Installed = ($NumEntries - $Failed)
	[int]$Elapsed = $StopWatch.Elapsed.TotalSeconds
	"✔️ installed $Installed of $NumEntries applications in $Elapsed sec"
	exit 0 # success
} catch {
	"⚠️ Error in line $($_.InvocationInfo.ScriptLineNumber): $($Error[0])"
	exit 1
}
```

*Generated by convert-ps2md.ps1 using the comment-based help of install-basic-apps.ps1*
