Pattern: Malformed class doc comment

Issue: -

## Description

Parses and verifies the class doc comment. Verifies that:

-   A class doc comment exists.
-   The comment uses the correct docblock style.
-   There are no blank lines after the class comment.
-   No tags are used in the docblock.

## Further Reading

* [PHP_CodeSniffer - Drupal.Commenting.ClassComment](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/Drupal/Sniffs/Commenting/ClassCommentSniff.php)