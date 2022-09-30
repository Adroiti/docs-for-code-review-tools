Pattern: Use of mismatched parameter for DSC

Issue: -

## Description

The `Get-TargetResource`, `Test-TargetResource` and `Set-TargetResource` functions of DSC Resource must have the same parameters.

## How

Correct the parameters for the functions in DSC resource.

Example of **incorrect** code:

``` PowerShell
function Get-TargetResource
{
    [OutputType([Hashtable])]
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name,

        [String]
        $TargetResource
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

Example of **correct** code:

``` PowerShell
function Get-TargetResource
{
    [OutputType([Hashtable])]
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name,

        [String]
        $TargetResource
    )
    ...
}

function Set-TargetResource
{
    param
    (
        [parameter(Mandatory = $true)]
        [String]
        $Name,

        [String]
        $TargetResource
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
        $Name,

        [String]
        $TargetResource
    )
    ...
}
```

## Further Reading

* [PSScriptAnalyzer - DSCUseIdenticalParametersForDSC](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/DSCUseIdenticalParametersForDSC.md)