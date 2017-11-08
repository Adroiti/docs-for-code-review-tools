Pattern: Unnecessary overriding method

Issue: -

## Description

Detects unnecessary overridden methods that simply call their parent. These methods are not required.

## Example

Example of **incorrect** code:

``` php
class SomeClass extends SomeParentClass {
  public function __construct($a, $b) {
    parent::__construct($a, $b);
  }
  
  public function init() {
    $this->connect_to_DB();
    $this->set_emulate_state();
    $this->start_profiler();
  }  
}
```
  
Example of **correct** code:

``` php
class SomeClass extends SomeParentClass {
  public function init() {
    $this->connect_to_DB();
    $this->set_emulate_state();
    $this->start_profiler();
  }
}
```

## Further Reading

* [PHP_CodeSniffer - Generic.CodeAnalysis.UselessOverridingMethod](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/CodeAnalysis/UselessOverridingMethodSniff.php)