Pattern: Incorrect use of cmdlet

Issue: -

## Description

Whenever we call a command, care should be taken that it is invoked with the correct syntax and parameters.

## How

Specify all mandatory parameters when calling commands.

Example of **incorrect** code:

``` PowerShell
Function Set-TodaysDate ()
{
	Set-Date
	...
}
```

Example of **correct** code:

``` PowerShell
Function Set-TodaysDate ()
{
	$date = Get-Date
	Set-Date -Date $date
	...
}
```

## Further Reading

* [PSScriptAnalyzer - UseCmdletCorrectly](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseCmdletCorrectly.md)