Pattern: Inconsistent line count between constants

Issue: -

## Description

Checks that there is a certain number of blank lines between constants.

Rule provides the following settings:

* `minLinesCountBeforeWithComment`: minimum number of lines before constant with a documentation comment or attribute
* `maxLinesCountBeforeWithComment`: maximum number of lines before constant with a documentation comment or attribute
* `minLinesCountBeforeWithoutComment`: minimum number of lines before constant without a documentation comment or attribute
* `maxLinesCountBeforeWithoutComment`: maximum number of lines before constant without a documentation comment or attribute

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Classes.ConstantSpacing](https://github.com/slevomat/coding-standard/blob/master/doc/classes.md#slevomatcodingstandardclassesconstantspacing-)