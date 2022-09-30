Pattern: Use of `*`/`$null` in module manifest

Issue: -

## Description

To improve the performance of module auto-discovery, module manifests should not use wildcards (`'*'`) or null (`$null`) in the following entries:
* `AliasesToExport`
* `CmdletsToExport`
* `FunctionsToExport`
* `VariablesToExport`

The use of wildcards or null has the potential to cause PowerShell to perform expensive work to analyse a module during module auto-discovery.

## How

Use an explicit list in the entries.

Suppose there are no functions in your module to export. Then,

Example of **incorrect** code:

``` PowerShell
FunctionsToExport = $null
```

Example of **correct** code:

``` PowerShell
FunctionToExport = @()
```

Suppose there are only two functions in your module, `Get-Foo` and `Set-Foo` that you want to export. Then,

Example of **incorrect** code:

``` PowerShell
FunctionsToExport = '*'
```

Example of **correct** code:

``` PowerShell
FunctionToExport = @(Get-Foo, Set-Foo)
```

## Further Reading

* [PSScriptAnalyzer - UseToExportFieldsInManifest](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseToExportFieldsInManifest.md)