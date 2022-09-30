Pattern: Missing standard function for DSC

Issue: -

## Description

All DSC resources are required to implement the correct functions.

For non-class based resources:
* `Set-TargetResource`
* `Test-TargetResource`
* `Get-TargetResource`

For class based resources:
* `Set`
* `Test`
* `Get`

## How

Add the missing functions to the resource.

Example of **incorrect** code:

``` PowerShell
function Get-TargetResource
{
    [OutputType([Hashtable])]
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name
    )
    ...
}

function Set-TargetResource
{
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name
    )
    ...
}
```
Example of **correct** code:

``` PowerShell
function Get-TargetResource
{
    [OutputType([Hashtable])]
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name
    )
    ...
}

function Set-TargetResource
{
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name
    )
    ...
}

function Test-TargetResource
{
    [OutputType([System.Boolean])]
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name
    )
    ...
}
```

Example of **incorrect** code:

``` PowerShell
[DscResource()]
class MyDSCResource
{
    [DscProperty(Key)]
    [string] $Name

    [void] Set()
    {
        ...
    }

    [bool] Test()
    {
        ...
    }
}

Example of **correct** code:

``` PowerShell
[DscResource()]
class MyDSCResource
{
    [DscProperty(Key)]
    [string] $Name

    [MyDSCResource] Get()
    {
        ...
    }

    [void] Set()
    {
        ...
    }

    [bool] Test()
    {
        ...
    }
}
```

## Further Reading

* [PSScriptAnalyzer - DSCStandardDSCFunctionsInResource](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/DSCStandardDSCFunctionsInResource.md)