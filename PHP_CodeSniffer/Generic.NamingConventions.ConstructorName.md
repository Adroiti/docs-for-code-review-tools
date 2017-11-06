Pattern: Use of _PHP 4_ constructor

Issue: -

## Description

Bans PHP 4 style constructors.

Favor PHP 5 constructor syntax, which uses `function __construct()`. Avoid PHP 4 constructor syntax, which uses `function ClassName()`.

## Further Reading

* [PHP_CodeSniffer - Generic.NamingConventions.ConstructorName](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/NamingConventions/ConstructorNameSniff.php)