Pattern: Missing `exit;` after `wp_redirect`/`wp_safe_redirect`

Issue: -

## Description

Requires `exit;` being called after `wp_redirect` and `wp_safe_redirect`.

## Further Reading

* [WordPressVIPMinimum.Security.ExitAfterRedirect](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Security/ExitAfterRedirectSniff.php)