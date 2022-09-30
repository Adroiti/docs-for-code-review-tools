Pattern: Use of reserved common parameter

Issue: -

## Description

You cannot use reserved common parameters in an advanced function.

## How

Change the name of the parameter.

Example of **incorrect** code:

``` PowerShell
function Test
{
    [CmdletBinding]
    Param
    (
        $ErrorVariable,
        $Parameter2
    )
}
```

Example of **correct** code:

``` PowerShell
function Test
{
    [CmdletBinding]
    Param
    (
        $Err,
        $Parameter2
    )
}
```

## Further Reading

* [PSScriptAnalyzer - ReservedParams](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/ReservedParams.md)