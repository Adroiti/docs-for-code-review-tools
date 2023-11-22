Pattern: Unused variable

Issue: -

## Description

Looks for unused variables.

Rule provides the following settings:

* `ignoreUnusedValuesWhenOnlyKeysAreUsedInForeach` (defaults to `false`): ignore unused `$value` in foreach when only `$key` is used

```php
foreach ($values as $key => $value) {
	echo $key;
}
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Variables.UnusedVariable](https://github.com/slevomat/coding-standard/blob/master/doc/variables.md#slevomatcodingstandardvariablesunusedvariable)