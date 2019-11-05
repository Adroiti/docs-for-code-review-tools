Pattern: Use of mismatched mandatory parameter for DSC

Issue: -

## Description

For script-based DSC resources, if a property is declared with attributes `Key` of `Required` in a `mof` file, then is should be present as a mandatory parameter in the corresponding `Get-TargetResource`, `Set-TargetResource` and `Test-TargetResource` functions.

## How

Make sure all the properties with `Key` and `Required` attributes have equivalent mandatory parameters in the `Get/Set/Test` functions.

Consider the following `mof` file.

```powershell
class WaitForAny : OMI_BaseResource
{
    [key, Description("Name of Resource on remote machine")]
    string Name;

    [required, Description("List of remote machines")]
    string NodeName[];
};
```

Example of **incorrect** code:

``` PowerShell
function Get-TargetResource
{
    [CmdletBinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Message
    )
}

function Set-TargetResource
{
    [CmdletBinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Message,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name
    )
}

function Test-TargetResource
{
    [CmdletBinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Message,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name
    )
}
```

Example of **correct** code:

``` PowerShell
function Get-TargetResource
{
    [CmdletBinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Message,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name
    )
}

function Set-TargetResource
{
    [CmdletBinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Message,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name
    )
}

function Test-TargetResource
{
    [CmdletBinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Message,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name
    )
}
```

## Further Reading

* [PSScriptAnalyzer - DSCUseIdenticalMandatoryParametersForDSC](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/DSCUseIdenticalMandatoryParametersForDSC.md)