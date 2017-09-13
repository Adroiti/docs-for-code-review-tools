Pattern: Lint/UnneededSplatExpansion

Issue: -

## Description

This cop checks for unneeded usages of splat expansion

### Example

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

* [RuboCop - Lint/UnneededSplatExpansion](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintunneededsplatexpansion)
