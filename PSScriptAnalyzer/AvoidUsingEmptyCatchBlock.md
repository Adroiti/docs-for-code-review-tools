Pattern: Use of empty catch block

Issue: -

## Description

Empty catch blocks are considered a poor design choice as they result in the errors occurring in a `try` block not being acted upon.

While this does not inherently lead to issues, they should be avoided wherever possible.

## How

Use `Write-Error` or `throw` statements within the catch block.

Example of **incorrect** code:

``` PowerShell
try
{
	1/0
}
catch [DivideByZeroException]
{
}
```

Example of **correct** code:

``` PowerShell
try
{
	1/0
}
catch [DivideByZeroException]
{
	Write-Error "DivideByZeroException"
}

try
{
	1/0
}
catch [DivideByZeroException]
{
	Throw "DivideByZeroException"
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingEmptyCatchBlock](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidUsingEmptyCatchBlock.md)