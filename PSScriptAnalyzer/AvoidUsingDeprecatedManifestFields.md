Pattern: Use of deprecated manifest field

Issue: -

## Description

In PowerShell 5.0, a number of fields in module manifest files (`.psd1`) have been changed.

The field `ModuleToProcess` has been replaced with the `RootModule` field.

## How

Replace `ModuleToProcess` with `RootModule` in the module manifest.

Example of **incorrect** code:

``` PowerShell
ModuleToProcess ='psscriptanalyzer'

ModuleVersion = '1.0'
```

Example of **correct** code:

``` PowerShell
RootModule ='psscriptanalyzer'

ModuleVersion = '1.0'
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingDeprecatedManifestFields](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/AvoidUsingDeprecatedManifestFields.md)