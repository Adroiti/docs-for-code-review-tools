Pattern: Reserved keyword as function parameter

Issue: -

## Description

Disallows function parameters using reserved keywords as names, as this can quickly become confusing when people use them in function calls using named parameters

* The sniff has modular error codes to allow for making exceptions for specific keywords.
    The error codes follow the following pattern: `[keyword]Found`.

## Further Reading

* [Universal.NamingConventions.NoReservedKeywordParameterNames](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universal)