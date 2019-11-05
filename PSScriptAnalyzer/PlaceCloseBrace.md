Pattern: Malformed close brace

Issue: -

## Description

Close brace placement should follow a consistent style. It should be on a new line by itself and should not be followed by an empty line.

## Configuration

```powershell
    Rules = @{
        PSPlaceCloseBrace = @{
            Enable = $true
            NoEmptyLineBefore = $false
            IgnoreOneLineBlock = $true
            NewLineAfter = $true
        }
    }
```

### Parameters

#### Enable: bool (Default value is `$false`)

Enable or disable the rule during ScriptAnalyzer invocation.

#### NoEmptyLineBefore: bool (Default value is `$false`)

Create violation if there is an empty line before a close brace.

#### IgnoreOneLineBlock: bool (Default value is `$true`)

Indicates if close braces in a one line block should be ignored or not.
E.g. $x = if ($true) { "test" } else { "test test" }
In the above example, if the property is set to true then the rule will not fire a violation.

#### NewLineAfter: bool (Default value is `$true`)

Indicates if a new line should follow a close brace. If set to true a close brace should be followed by a new line.

## Further Reading

* [PSScriptAnalyzer - PlaceCloseBrace](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/PlaceCloseBrace.md)