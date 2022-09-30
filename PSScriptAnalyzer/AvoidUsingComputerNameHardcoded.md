Pattern: Use of hard-coded computer name

Issue: -

## Description

The names of computers should never be hard-coded as this will expose sensitive information. The `ComputerName` parameter should never have a hard-coded value.

## How

Remove hard coded computer names.

Example of **incorrect** code:

``` PowerShell
Function Invoke-MyRemoteCommand ()
{
	Invoke-Command -Port 343 -ComputerName "hardcoderemotehostname"
}
```

Example of **correct** code:

``` PowerShell
Function Invoke-MyCommand ($ComputerName)
{
	Invoke-Command -Port 343 -ComputerName $ComputerName
}
```

Example of **incorrect** code:

``` PowerShell
Function Invoke-MyLocalCommand ()
{
	Invoke-Command -Port 343 -ComputerName "hardcodelocalhostname"
}
```

Example of **correct** code:

``` PowerShell
Function Invoke-MyLocalCommand ()
{
	Invoke-Command -Port 343 -ComputerName $env:COMPUTERNAME
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingComputerNameHardcoded](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidUsingComputerNameHardcoded.md)