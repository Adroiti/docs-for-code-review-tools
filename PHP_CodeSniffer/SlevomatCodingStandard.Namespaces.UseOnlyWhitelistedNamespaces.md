Pattern: Use of non-whitelisted namespace

Issue: -

## Description

Disallows uses of other than configured namespaces.

Rule provides the following settings:

* `namespacesRequiredToUse`: namespaces in this array are the only ones allowed to be used. E.g. root project namespace.
* `allowUseFromRootNamespace`: also allow using top-level namespace:

```php
use DateTimeImmutable;
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.UseOnlyWhitelistedNamespaces](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesuseonlywhitelistednamespaces)