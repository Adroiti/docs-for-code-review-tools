Pattern: Ambiguous range

Issue: -

## Description

Ranges have quite low precedence, which leads to unexpected behaviour when using a range with other operators. This rule avoids that by making ranges explicit by requiring parenthesis around complex range boundaries (anything that is not a basic literal: numerics, strings, symbols, etc.).

## Examples

```ruby
# bad
x || 1..2
(x || 1..2)
1..2.to_a

# good, unambiguous
1..2
'a'..'z'
:bar..:baz
MyClass::MIN..MyClass::MAX
@min..@max
a..b
-a..b

# good, ambiguity removed
x || (1..2)
(x || 1)..2
(x || 1)..(y || 2)
(1..2).to_a
```

## Further Reading

* [RuboCop - Lint/AmbiguousRange](https://docs.rubocop.org/rubocop/cops_lint.html#lintambiguousrange)
