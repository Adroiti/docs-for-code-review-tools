Pattern: Use of stand-alone PHP tag at the end of file

Issue: -

## Description

PHP 7.4 now supports stand-alone PHP tags at the end of a file (without new line). 

`<?php` at the end of the file (without trailing newline) will now be interpreted as an opening PHP tag. Previously it was interpreted either as `<? php` and resulted in a syntax error (with short_open_tag=1) or was interpreted as a literal `<?php` string (with short_open_tag=0).

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.Miscellaneous.NewPHPOpenTagEOF](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/Miscellaneous/NewPHPOpenTagEOFSniff.php)