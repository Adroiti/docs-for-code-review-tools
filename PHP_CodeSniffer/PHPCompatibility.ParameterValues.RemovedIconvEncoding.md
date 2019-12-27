Pattern: Passing deprecated `$type` values to `iconv_get_encoding()`

Issue: -

## Description

Detects passing deprecated `$type` values to `iconv_get_encoding()`. The iconv and mbstring configuration options related to encoding have been deprecated in favour of default_charset.

PHP version 5.6

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.RemovedIconvEncoding](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/RemovedIconvEncodingSniff.php)