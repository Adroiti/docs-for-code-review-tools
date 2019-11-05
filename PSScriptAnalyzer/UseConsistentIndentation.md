Pattern: Inconsistent indentation

Issue: -

## Description

Indentation should be consistent throughout the source file.

## Configuration

```powershell
    Rules = @{
        PSUseConsistentIndentation = @{
            Enable = $true
            IndentationSize = 4
            PipelineIndentation = 'IncreaseIndentationForFirstPipeline'
            Kind = 'space'
        }
    }
```

### Parameters

#### Enable: bool (Default value is `$false`)

Enable or disable the rule during ScriptAnalyzer invocation.

#### IndentationSize: int (Default value is `4`)

Indentation size in the number of space characters.

#### PipelineIndentation: string (Default value is `IncreaseIndentationForFirstPipeline`)

Whether to increase indentation after a pipeline for multi-line statements. The settings are:

- IncreaseIndentationForFirstPipeline (default): Indent once after the first pipeline and keep this indentation. Example:
```powershell
foo |
    bar |
    baz
```
- IncreaseIndentationAfterEveryPipeline: Indent more after the first pipeline and keep this indentation. Example:
```powershell
foo |
    bar |
        baz
```
- NoIndentation: Do not increase indentation. Example:
```powershell
foo |
bar |
baz
```

#### Kind: string (Default value is `space`)

Represents the kind of indentation to be used. Possible values are: `space`, `tab`. If any invalid value is given, the property defaults to `space`.

`space` means `IndentationSize` number of `space` characters are used to provide one level of indentation.
`tab` means a tab character, `\t`.

## Further Reading

* [PSScriptAnalyzer - UseConsistentIndentation](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseConsistentIndentation.md)