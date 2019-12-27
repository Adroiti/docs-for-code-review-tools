Pattern: Use of default `$encoding` parameter

Issue: -

## Description

As of PHP 5.4, the default character set for `htmlspecialchars()`, `htmlentities()`
and `html_entity_decode()` is now `UTF-8`, instead of `ISO-8859-1`.

PHP version 5.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.NewHTMLEntitiesEncodingDefault](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/NewHTMLEntitiesEncodingDefaultSniff.php)