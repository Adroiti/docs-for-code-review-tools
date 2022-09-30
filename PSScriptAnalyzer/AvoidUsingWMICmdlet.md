Pattern: Use of WMI cmdlet

Issue: -

## Description

As of PowerShell 3.0, the CIM cmdlets should be used over the WMI cmdlets.

The following cmdlets should not be used:
* `Get-WmiObject`
* `Remove-WmiObject`
* `Invoke-WmiObject`
* `Register-WmiEvent`
* `Set-WmiInstance`

Use the following cmdlets instead:
* `Get-CimInstance`
* `Remove-CimInstance`
* `Invoke-CimMethod`
* `Register-CimIndicationEvent`
* `Set-CimInstance`

The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, allowing for the management of Windows and non-Windows operating systems.

## How

Change to the equivalent CIM based cmdlet.
* `Get-WmiObject` -> `Get-CimInstance`
* `Remove-WmiObject` -> `Remove-CimInstance`
* `Invoke-WmiObject` -> `Invoke-CimMethod`
* `Register-WmiEvent` -> `Register-CimIndicationEvent`
* `Set-WmiInstance` -> `Set-CimInstance`

Example of **incorrect** code:

``` PowerShell
Get-WmiObject -Query 'Select * from Win32_Process where name LIKE "myprocess%"' | Remove-WmiObject
Invoke-WmiMethod ?Class Win32_Process ?Name "Create" ?ArgumentList @{ CommandLine = "notepad.exe" }
```

Example of **correct** code:

``` PowerShell
Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "myprocess%"' | Remove-CIMInstance
Invoke-CimMethod ?ClassName Win32_Process ?MethodName "Create" ?Arguments @{ CommandLine = "notepad.exe" }
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingWMICmdlet](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/AvoidUsingWMICmdlet.md)