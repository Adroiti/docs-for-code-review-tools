Pattern: Use of deprecated WP parameter

Issue: -

## Description

Checks for usage of deprecated parameters in WP functions and suggest alternative based on the parameter passed.

This rule will throw an error when usage of deprecated parameters is detected if the parameter was deprecated before the minimum supported WP version; a warning otherwise. By default, it is set to presume that a project will support the current WP version and up to three releases before.

## Further Reading

* [WordPress.WP.DeprecatedParameters](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/DeprecatedParametersSniff.php)