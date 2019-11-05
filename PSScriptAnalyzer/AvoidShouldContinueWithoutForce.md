Pattern: Use of `ShouldContinue` without force

Issue: -

## Description

Functions that use `ShouldContinue` should have a boolean force parameter to allow user to bypass it.

You can get more details by running `Get-Help about_Functions_CmdletBindingAttribute` and `Get-Help about_Functions_Advanced_Methods` command in Windows PowerShell.

## How

Call the `ShouldContinue` method in advanced functions when `ShouldProcess` method returns `$true`.

Example of **incorrect** code:

``` PowerShell
Function Test-ShouldContinue
{
    [CmdletBinding(SupportsShouldProcess=$true)]
    Param
    (
        $MyString = 'test'
    )

    if ($PsCmdlet.ShouldContinue("ShouldContinue Query", "ShouldContinue Caption"))
	{
        ...
    }
}
```

Example of **correct** code:

``` PowerShell
Function Test-ShouldContinue
{
    [CmdletBinding(SupportsShouldProcess=$true)]
    Param
    (
        $MyString = 'test',
        [Switch]$Force
    )

    if ($Force -or $PsCmdlet.ShouldContinue("ShouldContinue Query", "ShouldContinue Caption"))
	{
        ...
    }
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidShouldContinueWithoutForce](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/AvoidShouldContinueWithoutForce.md)