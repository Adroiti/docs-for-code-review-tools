Pattern: Unused parameter

Issue: -

## Description

This rule identifies parameters declared in a script, scriptblock, or function scope that have not been used in that scope. 

## How

Consider removing the unused parameter.

## Example

Example of **incorrect** code:

``` PowerShell
function Test-Parameter
{
	Param (
		$Parameter1,
		
		# this parameter is never called in the function
		$Parameter2
	)
	
	Get-Something $Parameter1
}
```

Example of **correct** code:

``` PowerShell
function Test-Parameter
{
	Param (
		$Parameter1,
		
		# now this parameter is being called in the same scope
		$Parameter2
	)
	
	Get-Something $Parameter1 $Parameter2
}
```

## Further Reading

* [PSScriptAnalyzer - ReviewUnusedParameter](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/ReviewUnusedParameter.md)