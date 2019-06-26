Pattern: Use of Filesystem operation

Issue: -

## Description

Disallows Filesystem writes. On the VIP Platform, web servers run in read-only mode. File operations are only allowed in the `/tmp/` directory and media uploads via the VIP Files Service.

## Further Reading

* [WordPress.VIP.FileSystemWritesDisallow](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#filesystem-operations)
* [WordPress.VIP.FileSystemWritesDisallow](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/VIP/FileSystemWritesDisallowSniff.php)