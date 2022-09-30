Pattern: Unused variable

Issue: -

## Description

Generally variables that are not used more than their assignments are considered wasteful and not needed.

## How

Remove the variables that are declared but not used.

Example of **incorrect** code:

``` PowerShell

function Test
{
    $declaredVar = "Declared and used"
    $declaredVar2 = "Not used"
    Write-Output $declaredVar
}
```

Example of **correct** code:

``` PowerShell

function Test
{
    $declaredVar = "Declared and used"
    Write-Output $declaredVar
}
```

## Further Reading

* [PSScriptAnalyzer - UseDeclaredVarsMoreThanAssignments](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseDeclaredVarsMoreThanAssignments.md)