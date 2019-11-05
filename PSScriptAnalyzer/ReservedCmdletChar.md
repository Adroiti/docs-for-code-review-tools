Pattern: Use of reserved character for cmdlet

Issue: -

## Description

You cannot use following reserved characters in a function or cmdlet name as these can cause parsing or runtime errors.

Reserved Characters include: 
```
#,(){}[]&/\\$^;:\"'<>|?@`*%+=~
```

## How

Remove reserved characters from names.

Example of **incorrect** code:

``` PowerShell
function CustomFunction[1]
{...}
```

Example of **correct** code:

``` PowerShell
function CustomFunction
{...}
```

## Further Reading

* [PSScriptAnalyzer - ReservedCmdletChar](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/ReservedCmdletChar.md)