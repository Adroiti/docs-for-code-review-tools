Pattern: Use of `ini_set()`

Issue: -

## Description

Detects use of the `ini_set()` function.

- Won't throw notices for "safe" ini directives as listed in the whitelist.
- Throws errors for ini directives listed in the blacklist.
- A warning will be thrown in all other cases.

## Further Reading

* [WordPress.PHP.IniSet](https://github.com/WordPress/WordPress-Coding-Standards/blob/develop/WordPress/Sniffs/PHP/IniSetSniff.php)