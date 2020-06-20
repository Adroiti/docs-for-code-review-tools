Pattern: Missing use of process block for pipeline command

Issue: -

## Description

Functions that support pipeline input should always handle parameter input in a process block. Unexpected behavior can result if input is handled directly in the body of a function where parameters declare pipeline support.

## Examples

Example of **incorrect** code:

``` PowerShell
Function Get-Number
{
	[CmdletBinding()]
	Param(
		[Parameter(ValueFromPipeline)]
		[int]
		$Number
	)
	
	$Number
}
```

#### Result

```
PS C:\> 1..5 | Get-Number
5
```

Example of **correct** code:

``` PowerShell
Function Get-Number
{
	[CmdletBinding()]
	Param(
		[Parameter(ValueFromPipeline)]
		[int]
		$Number
	)
	
	process
	{
		$Number
	}
}
```

#### Result

```
PS C:\> 1..5 | Get-Number
1
2
3
4
5
```

## Further Reading

* [PSScriptAnalyzer - UseProcessBlockForPipelineCommand](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseProcessBlockForPipelineCommand.md)