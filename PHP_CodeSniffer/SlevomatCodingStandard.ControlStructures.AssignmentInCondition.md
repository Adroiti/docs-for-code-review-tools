Pattern: Assignment in condition

Issue: -

## Description

Disallows assignments in `if`, `elseif` and `do-while` loop conditions:

```php
if ($file = findFile($path)) {

}
```

Assignment in `while` loop condition is specifically allowed because it's commonly used.

This is a great addition to already existing `SlevomatCodingStandard.ControlStructures.DisallowYodaComparison` because it prevents the danger of assigning something by mistake instead of using a comparison operator like `===`.

Rule provides the following settings:
* `ignoreAssignmentsInsideFunctionCalls`: ignores assignment inside function calls, like this:

```php
if (in_array(1, $haystack, $strict = true)) {

}
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.AssignmentInCondition](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresassignmentincondition)