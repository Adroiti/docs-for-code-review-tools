Pattern: Missing use of fully qualified global function

Issue: -

## Description

All references to global functions must be referenced via a fully qualified name.

Rule provides the following settings:

* `include`: list of global functions that must be referenced via FQN. If not set all functions are considered.
* `includeSpecialFunctions`: include complete list of PHP internal functions that could be optimized when referenced via FQN.
* `exclude`: list of global functions that are allowed not to be referenced via FQN.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.FullyQualifiedGlobalFunctions](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesfullyqualifiedglobalfunctions-)