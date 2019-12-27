Pattern: Use of unicode escape sequence

Issue: -

## Description

PHP 7.0 introduced a Unicode codepoint escape sequence.

Strings containing a literal `\u{` followed by an invalid sequence will cause a fatal error as of PHP 7.0.

PHP version 7.0

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.TextStrings.NewUnicodeEscapeSequence](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/TextStrings/NewUnicodeEscapeSequenceSniff.php)