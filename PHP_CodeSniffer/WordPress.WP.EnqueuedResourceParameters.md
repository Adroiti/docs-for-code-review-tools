Pattern: Misuse of `wp_register_script()`

Issue: -

## Description

Checks the enqueued 4th and 5th parameters to make sure the version and `in_footer` are set:
- If a source (`$src`) value is passed, then version (`$ver`) needs to have non-falsy value.
- If a source (`$src`) value is passed a check for in footer (`$in_footer`), warn the user if the value is falsy.

## Further Reading

* [WordPress Code Reference](https://developer.wordpress.org/reference/functions/wp_register_script)
* [WordPress.WP.EnqueuedResourceParameters](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/EnqueuedResourceParametersSniff.php)