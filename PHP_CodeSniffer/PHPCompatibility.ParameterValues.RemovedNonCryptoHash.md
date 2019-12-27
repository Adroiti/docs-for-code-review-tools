Pattern: Use of non-cryptographic hash

Issue: -

## Description

Detects usage of non-cryptographic hashes. The `hash_hmac()`, `hash_hmac_file()`, `hash_pbkdf2()`, and `hash_init()` (with `HASH_HMAC`) functions no longer accept non-cryptographic hashes.

PHP version 7.2

## Further Reading

* [PHP_CodeSniffer - PHPCompatibility.ParameterValues.RemovedNonCryptoHash](https://github.com/PHPCompatibility/PHPCompatibility/tree/develop/PHPCompatibility/Sniffs/ParameterValues/RemovedNonCryptoHashSniff.php)