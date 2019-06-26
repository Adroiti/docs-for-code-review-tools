Pattern: Use of deprecated WP class

Issue: -

## Description

Restricts the use of deprecated WordPress classes and suggests alternatives.

This rule will throw an error when usage of a deprecated class is detected if the class was deprecated before the minimum supported WP version; a warning otherwise. By default, it is set to presume that a project will support the current
WP version and up to three releases before.

## Further Reading

* [WordPress.WP.DeprecatedClasses](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/DeprecatedClassesSniff.php)