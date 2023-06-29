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

* [PSScriptAnalyzer - UseApprovedVerbs](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseApprovedVerbs.md)