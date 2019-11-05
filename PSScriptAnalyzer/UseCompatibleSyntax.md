Pattern: Use of incompatible syntax with targeted _PowerShell_ version

Issue: -

## Description

This rule identifies syntax elements that are incompatible with targeted PowerShell versions.

It cannot identify syntax elements incompatible with PowerShell 3/4 from PowerShell 3/4
due to those PowerShell versions not being able to parse the incompatible syntaxes.

```PowerShell
@{
    Rules = @{
        PSUseCompatibleSyntax = @{
            Enable = $true
            TargetVersions = @(
                "6.0",
                "5.1",
                "4.0"
            )
        }
    }
}
```

## Further Reading

* [PSScriptAnalyzer - UseCompatibleSyntax](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleSyntax.md)