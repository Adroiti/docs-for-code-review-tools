Pattern: Missing use of early exit

Issue: -

## Description

Requires use of early exit.

Rule provides the following settings:

* `ignoreStandaloneIfInScope`: ignores `if` that is standalone in scope, like this:

```php
foreach ($values as $value) {
	if ($value) {
		doSomething();
	}
}
```

* `ignoreOneLineTrailingIf`: ignores `if` that has one line content and is on the last position in scope, like this:

```php
foreach ($values as $value) {
	$value .= 'whatever';

	if ($value) {
		doSomething();
	}
}
```

* `ignoreTrailingIfWithOneInstruction`: ignores `if` that has only one instruction and is on the last position in scope, like this:

```php
foreach ($values as $value) {
	$value .= 'whatever';

	if ($value) {
		doSomething(function () {
			// Anything
		});
	}
}
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.ControlStructures.EarlyExit](https://github.com/slevomat/coding-standard/blob/master/doc/control-structures.md#slevomatcodingstandardcontrolstructuresearlyexit-)