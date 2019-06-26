Pattern: Use of high pagination limit

Issue: -

## Description

Using `posts_per_page` (or `numberposts`) with the value set to -1 or an unreasonably high number or setting `nopaging` to `true` opens up the potential for scaling issues if the query ends up querying thousands of posts.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#no-limit-queries)
* [WordPress.WP.PostsPerPage](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/PostsPerPageSniff.php)