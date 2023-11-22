Pattern: Malformed inline doc comment declaration

Issue: -

## Description

Reports invalid inline phpDocs with `@var`.

Rule provides the following settings:

* `allowDocCommentAboveReturn`: Allows documentation comments without variable name above `return` statement.
* `allowAboveNonAssignment`: Allows documentation comments above non-assignment if the line contains the right variable name.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Commenting.InlineDocCommentDeclaration](https://github.com/slevomat/coding-standard/blob/master/doc/commenting.md#slevomatcodingstandardcommentinginlinedoccommentdeclaration-)