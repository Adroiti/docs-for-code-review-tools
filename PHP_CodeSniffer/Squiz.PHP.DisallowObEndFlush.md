Pattern: Use of `ob_end_flush()`

Issue: -

## Description

Use of `ob_end_flush()` is not allowed; use `ob_get_contents()` and `ob_end_clean()` instead.

## Further Reading

* [PHP_CodeSniffer - Squiz.PHP.DisallowObEndFlush](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/PHP/DisallowObEndFlushSniff.php)