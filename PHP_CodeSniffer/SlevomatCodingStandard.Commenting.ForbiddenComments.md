Pattern: Forbidden comment

Issue: -

## Description

Reports forbidden comments in descriptions. Nothing is forbidden by default, the configuration is completely up to the user. It's recommended to forbid generated or inappropriate messages like:

* `Constructor.`
* `Created by PhpStorm.`

Rule provides the following settings:

* `forbiddenCommentPatterns`: allows to configure which comments are forbidden to be used. This is an array of regular expressions (PCRE) with delimiters.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Commenting.ForbiddenComments](https://github.com/slevomat/coding-standard/blob/master/doc/commenting.md#slevomatcodingstandardcommentingforbiddencomments-)