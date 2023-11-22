Pattern: Unreachable catch block

Issue: -

## Description

This rule finds unreachable catch blocks:

```php
try {
	doStuff();
} catch (\Throwable $e) {
	log($e);
} catch (\InvalidArgumentException $e) {
	// unreachable!
}
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Exceptions.DeadCatch](https://github.com/slevomat/coding-standard/blob/master/doc/exceptions.md#slevomatcodingstandardexceptionsdeadcatch)