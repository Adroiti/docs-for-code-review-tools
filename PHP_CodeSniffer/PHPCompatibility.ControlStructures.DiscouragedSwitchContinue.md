Pattern: Use of `continue` in `switch`

Issue: -

## Description

Detects use of `continue` in `switch` control structures.

As of PHP 7.3, PHP will throw a warning when `continue` is used to target a `switch` control structure. The sniff takes numeric arguments used with `continue` into account.

PHP version 7.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ControlStructures.DiscouragedSwitchContinue](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ControlStructures/DiscouragedSwitchContinueSniff.php)