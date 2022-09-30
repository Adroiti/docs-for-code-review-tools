Pattern: Use of multiple type attribute

Issue: -

## Description

Parameters should not have more than one type specifier. Multiple type specifiers on parameters
can cause runtime errors.

## How

Ensure each parameter has only 1 type specifier.

Example of **incorrect** code:

```powershell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [switch]
        [int]
        $Switch
    )
}
```

Example of **correct** code:

```powershell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [switch]
        $Switch
    )
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidMultipleTypeAttributes](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidMultipleTypeAttributes.md)