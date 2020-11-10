Pattern: Empty block

Issue: -

## Description

Such empty blocks are typically an oversight or we should provide a comment be clearer what we’re aiming for.

## Examples

```ruby
# bad
items.each { |item| }

# good
items.each { |item| puts item }
```

## Further Reading

* [RuboCop - Lint/EmptyBlock](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyblock)
