Pattern: Missing use of `Write-Verbose` in DSC function

Issue: -

## Description

It is a best practice to emit informative, verbose messages in DSC resource functions. This helps in debugging issues when a DSC configuration is executed.

## How

Make use of the `Write-Verbose` command.

Example of **incorrect** code:

``` PowerShell
Function Test-Function
{
    [CmdletBinding()]
    Param()
    ...
}
```

Example of **correct** code:

``` PowerShell
Function Test-Function
{
    [CmdletBinding()]
    Param()
    Write-Verbose "Verbose output"
    ...
}
```

## Further Reading

* [PSScriptAnalyzer - DSCUseVerboseMessageInDSCResource](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/DSCUseVerboseMessageInDSCResource.md)