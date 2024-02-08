Pattern: Silencing of error

Issue: -

## Description

Throws an error or warning when any code prefixed with an asperand is encountered.

## Example

``` php
if (@in_array($array, $needle))
{
	doSomething();
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.PHP.NoSilencedErrors](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/PHP/NoSilencedErrorsSniff.php)