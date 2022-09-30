Pattern: Malformed open brace

Issue: -

## Description

Open brace placement should follow a consistent style. It can either follow KR style (on same line) or the Allman style (not on same line).

## Configuration

```powershell
    Rules = @{
        PSPlaceOpenBrace = @{
            Enable = $true
            OnSameLine = $true
            NewLineAfter = $true
            IgnoreOneLineBlock = $true
        }
    }
```

### Parameters

#### Enable: bool (Default value is `$false`)

Enable or disable the rule during ScriptAnalyzer invocation.

#### OnSameLine: bool (Default value is `$true`)

Enforce open brace to be on the same line as that of its preceding keyword.

#### NewLineAfter: bool (Default value is `$true`)

Enforce a new line character after an open brace. The default value is true.

#### IgnoreOneLineBlock: bool (Default value is `$true`)

Indicates if open braces in a one line block should be ignored or not.
E.g. $x = if ($true) { "test" } else { "test test" }
In the above example, if the property is set to true then the rule will not fire a violation.

## Further Reading

* [PSScriptAnalyzer - PlaceOpenBrace](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/PlaceOpenBrace.md)