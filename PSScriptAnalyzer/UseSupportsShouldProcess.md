Pattern: Missing use of `SupportsShouldProcess`

Issue: -

## Description

This rule discourages manual declaration of `whatif` and `confirm` parameters in a function/cmdlet. These parameters are, however, provided automatically when a function declares a `CmdletBinding` attribute with `SupportsShouldProcess` as its named argument. 

Using `SupportsShouldProcess` not only provides these parameters but also some generic functionality that allows the function/cmdlet authors to provide the desired interactive experience while using the cmdlet.

## Examples

Example of **incorrect** code:

```PowerShell
function test {
    param(
        $param1,
        $confirm,
        $whatif
    )
}
```

Example of **correct** code:
```PowerShell
function test {
    [CmdletBinding(SupportsShouldProcess)]
    param(
        $param1
    )
}
```

## Further Reading

* [PSScriptAnalyzer - UseSupportsShouldProcess](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseSupportsShouldProcess.md)