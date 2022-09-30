Pattern: Use of plural noun for Cmdlet

Issue: -

## Description

Cmdlets should use singular nouns and not plurals.

## How

Change plurals to singular.

Example of **incorrect** code:

``` PowerShell
function Get-Files
{
    ...
}
```

Example of **correct** code:

``` PowerShell
function Get-File
{
    ...
}
```

## Further Reading

* [PowerShell Best Practices](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/PowerShellBestPractices.md)
* [PSScriptAnalyzer - UseSingularNouns](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseSingularNouns.md)