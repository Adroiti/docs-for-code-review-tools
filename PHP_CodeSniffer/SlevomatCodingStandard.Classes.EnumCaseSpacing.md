Pattern: Inconsistent enum case spacing

Issue: -

## Description

Checks that there is a certain number of blank lines between enum cases.

Rule provides the following settings:

* `minLinesCountBeforeWithComment`: minimum number of lines before enum case with a documentation comment or attribute
* `maxLinesCountBeforeWithComment`: maximum number of lines before enum case with a documentation comment or attribute
* `minLinesCountBeforeWithoutComment`: minimum number of lines before enum case without a documentation comment or attribute
* `maxLinesCountBeforeWithoutComment`: maximum number of lines before enum case without a documentation comment or attribute

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Classes.EnumCaseSpacing](https://github.com/slevomat/coding-standard/blob/master/doc/classes.md#slevomatcodingstandardclassesenumcasespacing-)