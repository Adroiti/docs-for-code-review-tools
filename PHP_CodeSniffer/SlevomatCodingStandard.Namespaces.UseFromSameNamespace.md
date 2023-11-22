Pattern: Use from same namespace

Issue: -

## Description

Prohibits uses from the same namespace:

```php
namespace Foo;

use Foo\Bar;
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.UseFromSameNamespace](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesusefromsamenamespace-)