# Help for take-screenshot.ps1 PowerShell Script

## Synopsis & Description
```powershell
take-screenshot.ps1 [<directory>]
```

Takes a single screenshot and saves it into the current/given directory.

## Syntax & Parameters
```powershell
/home/mf/PowerShell/Scripts/take-screenshot.ps1 [[-Directory] <String>] [<CommonParameters>]
```

```
-Directory <String>
    
    Required?                    false
    Position?                    1
    Default value                "$PWD"
    Accept pipeline input?       false
    Accept wildcard characters?  false
```

```
[<CommonParameters>]
    This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, 
    WarningVariable, OutBuffer, PipelineVariable, and OutVariable.
```

## Example
```powershell
PS>.\take-screenshot.ps1 C:\Temp
```


## Notes
Author: Markus Fleschutz · License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

*Generated from comment-based help of take-screenshot.ps1 by convert-ps2md.ps1*