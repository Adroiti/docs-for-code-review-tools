Pattern: Missing `PSCredential` type for Credential parameter

Issue: -

## Description

If the cmdlet or function has a `Credential` parameter, the parameter must accept the `PSCredential` type.

## How

Change the `Credential` parameter's type to be `PSCredential`.

Example of **incorrect** code:

``` PowerShell
function Credential([String]$Credential)
{
	...
}
```

Example of **correct** code:

``` PowerShell
function Credential([PSCredential]$Credential)
{
	...
}
```

## Further Reading

* [PSScriptAnalyzer - UsePSCredentialType](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UsePSCredentialType.md)