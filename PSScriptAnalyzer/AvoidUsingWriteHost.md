Pattern: Use of `Write-Host` cmdlet

Issue: -

## Description

The use of `Write-Host` is greatly discouraged unless in the use of commands with the `Show` verb.
The `Show` verb explicitly means 'show on the screen, with no other possibilities'.

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