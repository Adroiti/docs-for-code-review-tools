Pattern: Use of direct database query

Issue: -

## Description

You should almost never need to query database tables directly. Using WordPress APIs rather than rolling your own functions saves you time and assures compatibility with past and future versions of WordPress and PHP. It also makes code reviews go more smoothly because we know we can trust the APIs.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#direct-database-queries)