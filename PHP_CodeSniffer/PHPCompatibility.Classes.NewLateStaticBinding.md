Pattern: Use of late static binding

Issue: -

## Description

Detects use of late static binding as introduced in PHP 5.3.

Checks for:
- Late static binding as introduced in PHP 5.3.
- Late static binding being used outside of class scope (unsupported).

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Classes.NewLateStaticBinding](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Classes/NewLateStaticBindingSniff.php)