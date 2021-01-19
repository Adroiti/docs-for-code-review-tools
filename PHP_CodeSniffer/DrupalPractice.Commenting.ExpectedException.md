Pattern: Use of `@expectedExcpetion` tag

Issue: -

## Description

Checks that the PHPunit `@expectedExcpetion` tags are not used. Use `$this->setExpectedException()` or `$this->expectException()` instead.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.Commenting.ExpectedException](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/Commenting/ExpectedExceptionSniff.php)