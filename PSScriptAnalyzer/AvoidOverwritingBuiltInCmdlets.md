Pattern: Overwriting built-in cmdlet

Issue: -

## Description

This rule flags cmdlets that are available in a given edition/version of PowerShell on a given operating system which are overwritten by a function declaration. It works by comparing function declarations against a set of whitelists which ship with PSScriptAnalyzer. These whitelist files are used by other PSScriptAnalyzer rules.

## Configuration

To enable the rule to check if your script is compatible on PowerShell Core on Windows, put the following your settings file.


```PowerShell
@{
    'Rules' = @{
        'PSAvoidOverwritingBuiltInCmdlets' = @{
            'PowerShellVersion' = @("core-6.1.0-windows")
        }
    }
}
```

### Parameters

#### PowerShellVersion

The parameter `PowerShellVersion` is a list of whitelists that ship with PSScriptAnalyzer.

**Note**: The default value for `PowerShellVersion` is `"core-6.1.0-windows"` if PowerShell 6 or later is installed, and `"desktop-5.1.14393.206-windows"` if it is not.

## Further Reading

* [PSScriptAnalyzer - AvoidOverwritingBuiltInCmdlets](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/AvoidOverwritingBuiltInCmdlets.md)