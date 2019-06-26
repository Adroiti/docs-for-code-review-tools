Pattern: Use of DB-restricted function

Issue: -

## Description

Verifies that no database related PHP functions are used.

Avoid touching the database directly. If there is a defined function that can get the data you need, use it. Database abstraction (using functions instead of queries) helps keep your code forward-compatible and, in cases where results are cached in memory, it can be many times faster.

## Further Reading

* [WordPress PHP Coding Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/#database-queries)
* [WordPress.DB.RestrictedFunctions](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/DB/RestrictedFunctionsSniff.php)