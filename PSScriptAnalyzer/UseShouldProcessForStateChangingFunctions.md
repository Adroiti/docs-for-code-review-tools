Pattern: Missing `ShouldProcess` for state changing function

Issue: -

## Description

Functions whose verbs change system state should support `ShouldProcess`.

Verbs that should support `ShouldProcess`:
* `New`
* `Set`
* `Remove`
* `Start`
* `Stop`
* `Restart`
* `Reset`
* `Update`

## How

Include the `SupportsShouldProcess` argument in the `CmdletBinding` attribute.

Example of **incorrect** code:

``` PowerShell
	function Set-ServiceObject
	{
	    [CmdletBinding()]
		param
		(
			[string]
			$Parameter1
		)
		...
	}
```

Example of **correct** code:

``` PowerShell
	function Set-ServiceObject
	{
	    [CmdletBinding(SupportsShouldProcess = $true)]
	    param
		(
			[string]
			$Parameter1
		)
		...
	}
```

## Further Reading

* [PSScriptAnalyzer - UseShouldProcessForStateChangingFunctions](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseShouldProcessForStateChangingFunctions.md)