Pattern: Use of unapproved verb

Issue: -

## Description

Checks that all defined cmdlets use approved verbs. This is in line with PowerShell's best practices.

Approved verbs can be found by running the command `Get-Verb`.

## How

Change the verb in the cmdlet's name to an approved verb.

Example of **incorrect** code:

``` PowerShell
function Change-Item
{
    ...
}
````

Example of **correct** code:

``` PowerShell
function Update-Item
{
    ...
}
```

## Further Reading

* [PowerShell Best Practices](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/PowerShellBestPractices.md)
* [Approved Verbs for PowerShell Commands](https://docs.microsoft.com/powershell/developer/cmdlet/approved-verbs-for-windows-powershell-commands)
* [PSScriptAnalyzer - UseApprovedVerbs](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseApprovedVerbs.md)