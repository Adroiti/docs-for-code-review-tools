Pattern: Silenced PHP error

Issue: -

## Description

Discourage the use of the PHP error silencing operator.

This rule allows the error operator to be used with a select list
of white-listed functions, as no amount of error checking can prevent
PHP from throwing errors when those functions are used.

## Further Reading

* [WordPress.PHP.NoSilencedErrors](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/PHP/NoSilencedErrorsSniff.php)