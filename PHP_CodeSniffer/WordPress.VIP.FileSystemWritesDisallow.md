Pattern: Use of Filesystem operation

Issue: -

## Description

On the VIP Platform, web servers run in read-only mode. File operations are only allowed in the `/tmp/` directory and media uploads via the VIP Files Service.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#filesystem-operations)