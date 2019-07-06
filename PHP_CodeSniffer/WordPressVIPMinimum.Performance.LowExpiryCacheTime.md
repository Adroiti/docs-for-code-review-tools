Pattern: Low cache expiry time

Issue: -

## Description

Throws a warning when low cache times are set.

Browser caching can help to reduce server load by reducing the number of requests per page. For example, by setting the correct file headers on files that don’t change (static files like images, CSS, JavaScript etc) browsers will then cache these files on your visitor’s computer.

## Further Reading

* [WordPress - Optimization – Caching](https://wordpress.org/support/article/optimization-caching/#browser-caching)
* [WordPressVIPMinimum.Performance.LowExpiryCacheTime](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Performance/LowExpiryCacheTimeSniff.php)