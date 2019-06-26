Pattern: Malformed multiple statement alignment

Issue: -

## Description

Enforces alignment of the double arrow assignment operator for multi-item, multi-line arrays.

- Align the double arrow operator to the same column for each item in a multi-item array.
- Allows for setting a maxColumn property to aid in managing line-length.
- Allows for new line(s) before a double arrow (configurable).
- Allows for handling multi-line array items differently if so desired (configurable).

## Further Reading

* [WordPress PHP Coding Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/#indentation)
* [WordPress.Arrays.MultipleStatementAlignment](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/Arrays/MultipleStatementAlignmentSniff.php)