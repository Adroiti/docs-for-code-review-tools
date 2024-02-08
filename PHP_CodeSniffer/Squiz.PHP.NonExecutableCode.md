Pattern: Unreachable code

Issue: -

## Description

Unreachable code can never be executed because there exists no control flow path to the code from the rest of the program. It is generally considered undesirable for a number of reasons, including increased code size and increased time and effort for maintenance. Consider deleting unused code to resolve this issue.

## Example

Example of **incorrect** code:

``` php
switch ($number) {
	case 1:
		return $number . $this->ordinals['first'];
		do_something(); // unreachable
		break; 		// unreachable
	case 2:
		return $number . $this->ordinals['second'];
		break; 		// unreachable
}
```

Example of **correct** code:

```php
switch ($number) {
	case 1:
		return $number . $this->ordinals['first'];
	case 2:
		return $number . $this->ordinals['second'];
}
```

## Further Reading

* [PHP_CodeSniffer - Squiz.PHP.NonExecutableCode](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/PHP/NonExecutableCodeSniff.php)
