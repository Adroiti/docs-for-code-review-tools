Pattern: Use of `;` as line terminator

Issue: -

## Description

Lines should not end with a semicolon.

> [!NOTE]
> This rule is not enabled by default. The user needs to enable it through settings.

Example of **incorrect** code:

```powershell
Install-Module -Name PSScriptAnalyzer; $a = 1 + $b;
```

```powershell
Install-Module -Name PSScriptAnalyzer;
$a = 1 + $b
```

Example of **correct** code:

```powershell
Install-Module -Name PSScriptAnalyzer; $a = 1 + $b
```

```powershell
Install-Module -Name PSScriptAnalyzer
$a = 1 + $b
```

## Configuration

```powershell
Rules = @{
    PSAvoidSemicolonsAsLineTerminators  = @{
        Enable     = $true
    }
}
```

### Parameters

#### Enable: bool (Default value is `$false`)

Enable or disable the rule during ScriptAnalyzer invocation.

## Further Reading

* [PSScriptAnalyzer - AvoidSemicolonsAsLineTerminators](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidSemicolonsAsLineTerminators.md)