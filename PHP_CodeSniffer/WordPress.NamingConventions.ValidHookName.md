Pattern: Invalid WP hook name

Issue: -

## Description

Use lowercase letters in action and filter names. Separate words via underscores.

This rule is only testing the hook invoke functions as when using `add_action`/`add_filter` you can't influence the hook name. Hook names invoked with `do_action_deprecated()` and `apply_filters_deprecated()` are ignored.

## Further Reading

* [WordPress PHP Coding Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/#naming-conventions)
* [WordPress.NamingConventions.ValidHookName](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/NamingConventions/ValidHookNameSniff.php)