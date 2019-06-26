Pattern: Incorrect use of type cast

Issue: -

## Description

Verifies the correct usage of type cast keywords.

Type casts should be:
- lowercase;
- short form, i.e. (bool) not (boolean);
- normalized, i.e. (float) not (real).

Additionally, the use of the (unset) and (binary) casts is discouraged.

## Further Reading

* [WordPress.PHP.TypeCasts](https://make.wordpress.org/core/handbook/best-practices/....)
* [WordPress.PHP.TypeCasts](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/PHP/TypeCastsSniff.php)