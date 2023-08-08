Pattern: Unnecessary splat expansion

Issue: -

## Description

This rule checks for unnecessary usages of splat expansion.

## Examples

```ruby
# bad

a = *[1, 2, 3]
a = *'a'
a = *1

begin
  foo
rescue *[StandardError, ApplicationError]
  bar
end

case foo
when *[1, 2, 3]
  bar
else
  baz
end
```
```ruby
# good

c = [1, 2, 3]
a = *c
a, b = *c
a, *b = *c
a = *1..10
a = ['a']

begin
  foo
rescue StandardError, ApplicationError
  bar
end

case foo
when *[1, 2, 3]
  bar
else
  baz
end
```

## Further Reading

* [RuboCop - Lint/UnneededSplatExpansion](https://docs.rubocop.org/rubocop/cops_lint.html#lintunneededsplatexpansion)
