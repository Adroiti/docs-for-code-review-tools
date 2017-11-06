Pattern: Use of `$this` in static method

Issue: -

## Description

Checks for usage of `$this` in static methods, which will cause runtime errors.

## Further Reading

* [PHP_CodeSniffer - Squiz.Scope.StaticThisUsage](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Scope/StaticThisUsageSniff.php)