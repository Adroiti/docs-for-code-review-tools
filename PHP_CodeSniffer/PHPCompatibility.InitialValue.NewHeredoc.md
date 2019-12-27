Pattern: Use of new heredoc

Issue: -

## Description

Detects a heredoc being used to set an initial value.

As of PHP 5.3.0, it's possible to initialize static variables, class properties
and constants declared using the `const` keyword, using the Heredoc syntax.
And while not documented, heredoc initialization can now also be used for function param defaults.

These heredocs (still) cannot contain variables. That's, however, outside the scope of the
PHPCompatibility library until such time as there is a PHP version in which this would be accepted.

PHP version 5.3

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.InitialValue.NewHeredoc](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/InitialValue/NewHeredocSniff.php)