Pattern: Leading backslash in import `use`

Issue: -

## Description

Verifies that a name being imported in an import `use` statement does not start with a leading backslash.

Names in import `use` statements should always be fully qualified, so a leading backslash is not needed and it is strongly recommended not to use one.

This sniff handles all types of import use statements supported by PHP, in contrast to other sniffs for the same in, for instance, the PHPCS native `PSR12` or the Slevomat standard, which are incomplete.

## Further Reading

* [Universal.UseStatements.NoLeadingBackslash](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universal)