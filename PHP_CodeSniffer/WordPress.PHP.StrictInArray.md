Pattern: Use of `in_array()` without strict parameter

Issue: -

## Description

Flags calling `in_array()`, `array_search()` and `array_keys()` without `true` as the third parameter.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#using-in_array-without-strict-parameter)
* [WordPress.PHP.StrictInArray](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/PHP/StrictInArraySniff.php)