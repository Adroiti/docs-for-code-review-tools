Pattern: Use of incompatible cmdlet with targeted _PowerShell_ version

Issue: -

## Description

This rule flags cmdlets that are not available in a given Edition/Version of PowerShell on a given Operating System. It works by comparing a cmdlet against a set of whitelists which ship with PSScriptAnalyzer.

To enable the rule to check if your script is compatible on PowerShell Core on Windows, put the following your settings file:

```PowerShell
@{
    'Rules' = @{
        'PSUseCompatibleCmdlets' = @{
            'compatibility' = @("core-6.1.0-windows")
        }
    }
}
```

The parameter `compatibility` is a list that contain any of the following

- desktop-2.0-windows
- desktop-3.0-windows
- desktop-4.0-windows (taken from Windows Server 2012R2)
- desktop-5.1.14393.206-windows
- core-6.1.0-windows (taken from Windows 10 - 1803)
- core-6.1.0-linux (taken from Ubuntu 18.04)
- core-6.1.0-linux-arm (taken from Raspbian)
- core-6.1.0-macos

Usually, patched versions of PowerShell have the same cmdlet data, therefore only settings of major and minor versions of PowerShell are supplied.

## Further Reading

* [PSScriptAnalyzer - UseCompatibleCmdlets](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCmdlets.md)