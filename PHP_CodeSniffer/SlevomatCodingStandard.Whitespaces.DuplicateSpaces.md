Pattern: Duplicate spaces

Issue: -

## Description

Checks duplicate spaces anywhere because there aren't sniffs for every part of code to check formatting.

Rule provides the following settings:

* `ignoreSpacesBeforeAssignment`: to allow multiple spaces to align assignments.
* `ignoreSpacesInAnnotation`: to allow multiple spaces to align annotations.
* `ignoreSpacesInComment`: to allow multiple spaces to align content of the comment.
* `ignoreSpacesInParameters`: to allow multiple spaces to align parameters.
* `ignoreSpacesInMatch`: to allow multiple spaces to align `match` expressions.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Whitespaces.DuplicateSpaces](https://github.com/slevomat/coding-standard/blob/master/doc/whitespaces.md#slevomatcodingstandardwhitespacesduplicatespaces-)