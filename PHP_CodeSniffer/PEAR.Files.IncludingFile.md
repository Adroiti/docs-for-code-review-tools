Pattern: Malformed file inclusion

Issue: -

## Description

Ensure `include_once` is used in conditional situations and `require_once` is used elsewhere.

Also checks that brackets do not surround the file being included.

## Further Reading

* [PHP_CodeSniffer - PEAR.Files.IncludingFile](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/PEAR/Sniffs/Files/IncludingFileSniff.php)