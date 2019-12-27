Pattern: Use of short list syntax

Issue: -

## Description

Detects short list syntax for symmetric array destructuring.

The shorthand array syntax (`[]`) may now be used to destructure arrays for
assignments (including within `foreach`), as an alternative to the existing
`list()` syntax, which is still supported.

PHP version 7.1

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Lists.NewShortList](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Lists/NewShortListSniff.php)