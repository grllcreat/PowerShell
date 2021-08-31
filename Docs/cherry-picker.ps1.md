# Help for cherry-picker.ps1 PowerShell Script

## Synopsis & Description
```powershell
cherry-picker.ps1 [<commit-id>] [<commit-message>] [<branches>] [<repo-dir>]
```

Cherry-picks a Git commit into one or more branches (branch names need to be separated by spaces).
NOTE: in case of merge conflicts the script stops immediately!

## Syntax & Parameters
```powershell
/home/mf/PowerShell/Scripts/cherry-picker.ps1 [[-CommitID] <String>] [[-CommitMessage] <String>] [[-Branches] <String>] [[-RepoDir] <String>] [<CommonParameters>]
```

```
-CommitID <String>
    
    Required?                    false
    Position?                    1
    Default value                
    Accept pipeline input?       false
    Accept wildcard characters?  false
```

```
-CommitMessage <String>
    
    Required?                    false
    Position?                    2
    Default value                
    Accept pipeline input?       false
    Accept wildcard characters?  false
```

```
-Branches <String>
    
    Required?                    false
    Position?                    3
    Default value                
    Accept pipeline input?       false
    Accept wildcard characters?  false
```

```
-RepoDir <String>
    
    Required?                    false
    Position?                    4
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
PS>.\cherry-picker.ps1 93849f889 "Fix typo" "v1 v2 v3"
```


## Notes
Author: Markus Fleschutz · License: CC0

## Related Links
https://github.com/fleschutz/PowerShell

*Generated from comment-based help of cherry-picker.ps1 by convert-ps2md.ps1*