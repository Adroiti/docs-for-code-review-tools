Pattern: Use of `Invoke-Expression`

Issue: -

## Description

Care must be taken when using the `Invoke-Expression` command. The `Invoke-Expression` executes the specified string and returns the results.

Code injection into your application or script can occur if the expression passed as a string includes any data provided from the user.

## How

Remove the use of `Invoke-Expression`.

Example of **incorrect** code:

``` PowerShell
Invoke-Expression "Get-Process"
```

Example of **correct** code:

``` PowerShell
Get-Process
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingInvokeExpression](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidUsingInvokeExpression.md)