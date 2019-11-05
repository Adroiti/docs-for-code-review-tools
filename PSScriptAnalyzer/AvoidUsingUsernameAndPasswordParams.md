Pattern: Use of Username/Password parameter

Issue: -

## Description

Either set the type of the Password parameter to `SecureString` or replace the Username and Password parameters with a Credential parameter of type `PSCredential`. If using a Credential parameter in PowerShell 4.0 or earlier, please define a credential transformation attribute after the `PSCredential` type attribute.


## How

Change the parameter to type `PSCredential`.

Example of **incorrect** code:

``` PowerShell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [String]
        $Username,
        [SecureString]
        $Password
    )
    ...
}
```

Example of **correct** code:

``` PowerShell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [PSCredential]
        $Credential
    )
    ...
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingUsernameAndPasswordParams](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/AvoidUsingUsernameAndPasswordParams.md)