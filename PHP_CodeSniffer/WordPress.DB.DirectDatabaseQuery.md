Pattern: Use of direct database query

Issue: -

## Description

You should almost never need to query database tables directly. Using WordPress APIs rather than rolling your own functions saves you time and assures compatibility with past and future versions of WordPress and PHP. It also makes code reviews go more smoothly because we know we can trust the APIs.

## Further Reading

* [VIP Go - Direct Database Queries](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#direct-database-queries)
* [WordPress.DB.DirectDatabaseQuery](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/DB/DirectDatabaseQuerySniff.php)