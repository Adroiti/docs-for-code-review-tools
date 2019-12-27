Pattern: Use of default `Iconv`/`Mbstring` function

Issue: -

## Description

Detects calls to `Iconv` and `Mbstring` functions with the optional `$charset`/`$encoding` parameter not set.

The default value for the iconv `$charset` and the MbString  $encoding` parameters was changed
in PHP 5.6 to the value of `default_charset`, which defaults to `UTF-8`.

Previously, the iconv functions would default to the value of `iconv.internal_encoding`;
The Mbstring functions would default to the return value of `mb_internal_encoding()`.
In both case, this would normally come down to `ISO-8859-1`.

PHP version 5.6

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.NewIconvMbstringCharsetDefault](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/NewIconvMbstringCharsetDefaultSniff.php)