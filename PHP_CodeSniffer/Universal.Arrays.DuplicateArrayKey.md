Pattern: Duplicate key in array declaration

Issue: -

## Description

Detects duplicate array keys in array declarations.

The rule will make a distinction between keys which will be duplicate in all PHP version and (numeric) keys which will only be a duplicate key in PHP < 8.0 or PHP >= 8.0.


## Further Reading

* [Universal.Arrays.DuplicateArrayKey](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universalarraysduplicatearraykey-books)