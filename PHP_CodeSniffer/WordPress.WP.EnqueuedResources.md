Pattern: Missing use of enqueued resource

Issue: -

## Description

Makes sure scripts and styles are enqueued and not explicitly echo'ed.

Inlining images, scripts or styles has been a common work around for performance problems related to HTTP 1.x As more and more of the web is now served via newer protocols (SPDY, HTTP 2.0) these techniques are now detrimental as they cannot be cached and require to be sent every time with the parent resource.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#inline-resources)
* [WordPress.WP.EnqueuedResources](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/EnqueuedResourcesSniff.php)