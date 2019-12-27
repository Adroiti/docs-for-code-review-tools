Pattern: Use of `parent` inside a class without parent

Issue: -

## Description

Using `parent` inside a class without parent is deprecated since PHP 7.4. This will throw a compile-time error in the future. Currently an error will only be generated if/when the parent is accessed at run-time.

PHP version 7.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Classes.RemovedOrphanedParent](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Classes/RemovedOrphanedParentSniff.php)