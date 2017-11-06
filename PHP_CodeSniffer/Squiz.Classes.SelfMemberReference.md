Pattern: Invalid self member reference

Issue: -

## Description

Tests self member references.

Verifies that:
- `self::` is used instead of `Self::`
- `self::` is used for local static member reference
- `self::` is used instead of `self ::`

## Further Reading

* [PHP_CodeSniffer - Squiz.Classes.SelfMemberReference](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Classes/SelfMemberReferenceSniff.php)