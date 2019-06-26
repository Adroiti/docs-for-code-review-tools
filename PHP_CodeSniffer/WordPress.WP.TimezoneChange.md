Pattern: Manipulating the timezone server-side

Issue: -

## Description

Using `date_default_timezone_set()` and similar isn’t allowed because it conflicts with stats and other systems. Developers instead should use WordPress’s internal timezone support.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#manipulating-the-timezone-server-side)
* [WordPress.WP.TimezoneChange](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/WP/TimezoneChangeSniff.php)