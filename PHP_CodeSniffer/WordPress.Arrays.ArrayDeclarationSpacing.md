Pattern: Inconsistent array spacing

Issue: -

## Description

Enforces WordPress array spacing format.

- Check for no space between array keyword and array opener.
- Check for no space between the parentheses of an empty array.
- Checks for one space after the array opener / before the array closer in single-line arrays.
- Checks that associative arrays are multi-line.
- Checks that each array item in a multi-line array starts on a new line.
- Checks that the array closer in a multi-line array is on a new line.

## Further Reading

* [WordPress PHP Coding Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/#indentation)
* [WordPress.Arrays.ArrayDeclarationSpacing](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/Arrays/ArrayDeclarationSpacingSniff.php)