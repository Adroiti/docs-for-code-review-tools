Pattern: Use of plain text for password

Issue: -

## Description

Password parameters that take in plain text will expose passwords and compromise the security of your system. Passwords should be stored in the `SecureString` type.

The following parameters are considered password parameters (this is not case sensitive):
* Password
* Pass
* Passwords
* Passphrase
* Passphrases
* PasswordParam

If a parameter is defined with a name in the above list, it should be declared with type `SecureString`.

## How

Change the type to `SecureString`.

Example of **incorrect** code:

``` PowerShell
function Test-Script
{
    [CmdletBinding()]
    Param
    (
        [string]
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
        [SecureString]
        $Password
    )
    ...
}
```

## Further Reading

* [PSScriptAnalyzer - AvoidUsingPlainTextForPassword](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/AvoidUsingPlainTextForPassword.md)