Pattern: Use of `orderby => rand`

Issue: -

## Description

MySQL queries that use `ORDER BY RAND()` can be pretty challenging and slow on large datasets. An alternate option can be to retrieve 100 posts and pick one at random.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#order-by-rand)
