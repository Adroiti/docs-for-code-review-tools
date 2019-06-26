Pattern: Use of `orderby => rand`

Issue: -

## Description

Flags uses of `orderby => rand`. MySQL queries that use `ORDER BY RAND()` can be pretty challenging and slow on large datasets. An alternate option can be to retrieve 100 posts and pick one at random.

## Further Reading

* [WordPress.VIP.OrderByRand](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#order-by-rand)
* [WordPress.VIP.OrderByRand](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/VIP/OrderByRandSniff.php)