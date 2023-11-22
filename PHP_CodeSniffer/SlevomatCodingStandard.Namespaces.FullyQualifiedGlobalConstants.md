Pattern: Missing use of fully qualified global constant

Issue: -

## Description

All references to global constants must be referenced via a fully qualified name.

Rule provides the following settings:

* `include`: list of global constants that must be referenced via FQN. If not set all constants are considered.
* `exclude`: list of global constants that are allowed not to be referenced via FQN.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.FullyQualifiedGlobalConstants](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesfullyqualifiedglobalconstants-)