Pattern: Use of leading backslash in `use`

Issue: -

## Description

Disallows leading backslash in use statement:

```php
use \Foo\Bar;
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.UseDoesNotStartWithBackslash](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesusedoesnotstartwithbackslash-)