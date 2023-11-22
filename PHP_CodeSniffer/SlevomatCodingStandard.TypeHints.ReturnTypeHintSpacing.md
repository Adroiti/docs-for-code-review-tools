Pattern: Inconsistent return type hint spacing

Issue: -

## Description

Enforces consistent formatting of return typehints, like this:

```php
function foo(): ?int
```

Rule provides the following settings:

* `spacesCountBeforeColon`: the number of spaces expected between closing brace and colon.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.TypeHints.ReturnTypeHintSpacing](https://github.com/slevomat/coding-standard/blob/master/doc/type-hints.md#slevomatcodingstandardtypehintsreturntypehintspacing-)