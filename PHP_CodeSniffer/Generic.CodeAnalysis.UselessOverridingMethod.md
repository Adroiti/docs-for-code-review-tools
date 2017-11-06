Pattern: Unnecessary overriding method

Issue: -

## Description

Detects unnecessary overridden methods that simply call their parent. These methods are not required.

## Example

``` php
class FooBar {
  public function __construct($a, $b) {
    parent::__construct($a, $b);
  }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UselessOverridingMethod](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UselessOverridingMethodSniff.php)