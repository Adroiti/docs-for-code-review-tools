Pattern: Use of deprecated WP functions

Issue: -

## Description

Restricts the use of various deprecated WordPress functions and suggests alternatives.

This sniff will throw an error when usage of deprecated functions is detected if the function was deprecated before the minimum supported WP version; a warning otherwise. By default, it is set to presume that a project will support the current
WP version and up to three releases before.

## Further Reading

* [WordPress.WP.DeprecatedFunctions](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/DeprecatedFunctionsSniff.php)