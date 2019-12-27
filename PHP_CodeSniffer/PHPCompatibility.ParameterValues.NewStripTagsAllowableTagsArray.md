Pattern: Use of `$allowable_tags` as array for `strip_tags()`

Issue: -

## Description

As of PHP 7.4, `strip_tags()` now also accepts an array of `$allowable_tags`.

PHP version 7.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.NewStripTagsAllowableTagsArray](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/NewStripTagsAllowableTagsArraySniff.php)