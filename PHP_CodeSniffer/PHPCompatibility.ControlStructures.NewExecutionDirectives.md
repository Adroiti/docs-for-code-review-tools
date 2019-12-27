Pattern: Malformed execution directive

Issue: -

## Description

Checks for valid execution directives set with `declare()`.

The sniff contains three distinct checks:
- Check if the execution directive used is valid. PHP currently only supports
  three execution directives.
- Check if the execution directive used is available in the PHP versions
  for which support is being checked.
  In the case of the `encoding` directive on PHP 5.3, support is conditional
  on the `--enable-zend-multibyte` compilation option. This will be indicated as such.
- Check whether the value for the directive is valid.

PHP version All.

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ControlStructures.NewExecutionDirectives](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ControlStructures/NewExecutionDirectivesSniff.php)