Pattern: Use of null or empty `HelpMessage` attribute

Issue: -

## Description

The value of the `HelpMessage` attribute should not be an empty string or a null value as this causes PowerShell's interpreter to throw an error when executing the function or cmdlet.

## How

Specify a value for the `HelpMessage` attribute.

## Example

Example of **incorrect** code:

``` PowerShell
Function BadFuncEmptyHelpMessageEmpty
{
	Param(
		[Parameter(HelpMessage='')]
		[String]
		$Param
	)

	$Param
}

Function BadFuncEmptyHelpMessageNull
{
	Param(
		[Parameter(HelpMessage=$null)]
		[String]
		$Param
	)

	$Param
}

Function BadFuncEmptyHelpMessageNoAssignment
{
	Param(
		[Parameter(HelpMessage)]
		[String]
		$Param
	)

	$Param
}
```

Example of **correct** code:

``` PowerShell
Function GoodFuncHelpMessage
{
	Param(
		[Parameter(HelpMessage='This is helpful')]
		[String]
		$Param
	)

	$Param
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidNullOrEmptyHelpMessageAttribute](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidNullOrEmptyHelpMessageAttribute.md)