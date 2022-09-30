Pattern: Missing use of `$using:` in new runspaces

Issue: -

## Description

If a ScriptBlock is intended to be run in a new RunSpace, variables inside it should use `$using:` scope modifier, or be initialized within the ScriptBlock.

This applies to:

- Invoke-Command *
- Workflow { InlineScript {}}
- Foreach-Object **
- Start-Job
- Start-ThreadJob
- The `Script` resource in DSC configurations, specifically for the `GetScript`, `TestScript` and `SetScript` properties

\* Only with the -ComputerName or -Session parameter.  
\*\* Only with the -Parallel parameter

## How

Within the ScriptBlock, instead of just using a variable from the parent scope, you have to add the `using:` scope modifier to it.

## Examples

Example of **incorrect** code:

```PowerShell
$var = "foo"
1..2 | ForEach-Object -Parallel { $var }
```

Example of **correct** code:

```PowerShell
$var = "foo"
1..2 | ForEach-Object -Parallel { $using:var }
```

## More correct examples

```powershell
$bar = "bar"
Invoke-Command -ComputerName "foo" -ScriptBlock { $using:bar }
```

```powershell
$bar = "bar"
$s = New-PSSession -ComputerName "foo"
Invoke-Command -Session $s -ScriptBlock { $using:bar }
```

```powershell
# Remark: Workflow is supported on Windows PowerShell only
Workflow { 
    $foo = "foo"
    InlineScript { $using:foo }
}
```

```powershell
$foo = "foo"
Start-ThreadJob -ScriptBlock { $using:foo }
Start-Job -ScriptBlock {$using:foo }
```

## Further Reading

* [PSScriptAnalyzer - UseUsingScopeModifierInNewRunspaces](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseUsingScopeModifierInNewRunspaces.md)