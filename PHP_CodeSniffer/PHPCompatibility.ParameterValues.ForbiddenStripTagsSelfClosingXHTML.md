Pattern: Use of self-closing XHTML tag in `strip_tags()`

Issue: -

## Description

Since PHP 5.3.4, `strip_tags()` ignores self-closing XHTML tags in `allowable_tags`.

PHP version 5.3.4

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.ForbiddenStripTagsSelfClosingXHTML](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/ForbiddenStripTagsSelfClosingXHTMLSniff.php)