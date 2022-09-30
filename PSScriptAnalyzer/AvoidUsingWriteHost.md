Pattern: Use of `Write-Host` cmdlet

Issue: -

## Description

`Write-Host` is host-specific, so its implementation might vary unpredictably. Also, prior to PowerShell 5.0, `Write-Host` did not write to a stream, so users cannot suppress it, capture its value, or redirect it.

Commands with the `Show` verb do not have this check applied.

## How

Replace `Write-Host` with `Write-Output` or `Write-Verbose` depending on whether the intention is logging or returning one or multiple objects.

Example of **incorrect** code:

``` PowerShell
function Get-MeaningOfLife
{
	...
	Write-Host "Computing the answer to the ultimate question of life, the universe and everything"
	...
	Write-Host 42
}
```

Example of **correct** code:

``` PowerShell
function Get-MeaningOfLife
{
	[CmdletBinding()]Param() # to make it possible to set the VerbosePreference when calling the function
	...
	Write-Verbose "Computing the answer to the ultimate question of life, the universe and everything"
	...
	Write-Output 42
}

function Show-Something
{
    Write-Host "show something on screen";
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingWriteHost](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidUsingWriteHost.md)