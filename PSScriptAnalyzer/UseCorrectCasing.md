Pattern: Incorrect casing for Cmdlet/Function

Issue: -

## Description

PowerShell is case insensitive where applicable. The casing of cmdlet names does not matter but this rule ensures that the casing matches for consistency and also because most cmdlets start with an upper case and using that improves readability to the human eye.

## How

Use exact casing of the cmdlet, e.g. `Invoke-Command`.

Example of **incorrect** code:

``` PowerShell
invoke-command { 'test' }
}
```

Example of **correct** code:

``` PowerShell
Invoke-Command { 'test' }
}
```

## Further Reading

* [PSScriptAnalyzer - UseCorrectCasing](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseCorrectCasing.md)