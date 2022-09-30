Pattern: Line if too long

Issue: -

## Description

Your source code should not contain very long lines. The default wrapping in most tools disrupts the visual structure of the code, making it more difficult to understand.

## Configuration

```powershell
    Rules = @{
        PSAvoidLongLines  = @{
            Enable     = $true
            LineLength = 120
        }
    }
```

### Parameters

#### Enable: bool (Default value is `$false`)

Enable or disable the rule during ScriptAnalyzer invocation.

#### MaximumLineLength: int (Default value is 120)

Optional parameter to override the default maximum line length.

## Further Reading

* [PSScriptAnalyzer - AvoidLongLines](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidLongLines.md)