Pattern: Use of non-lowercase keyword

Issue: -

## Description

Detect usage of `self`, `parent` and `static` and verify they are lowercase.

Prior to PHP 5.5, cases existed where the `self`, `parent`, and `static` keywords
were treated in a case sensitive fashion.

PHP version 5.5

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Keywords.CaseSensitiveKeywords](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Keywords/CaseSensitiveKeywordsSniff.php)