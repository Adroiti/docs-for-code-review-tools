Pattern: Use of trailing multi-line ternary operator

Issue: -

## Description

Ternary operator has to be reformatted when the operator is not leading the line.

```php
# wrong
$t = $someCondition ?
	$thenThis :
	$otherwiseThis;

# correct
$t = $someCondition
	? $thenThis
	: $otherwiseThis;
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.DisallowTrailingMultiLineTernaryOperator](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresdisallowtrailingmultilineternaryoperator-)