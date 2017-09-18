Pattern: Duplicate hash key

Issue: -

## Description

This rule checks for duplicated keys in hash literals. This rule mirrors a warning in Ruby 2.2.

## Examples

```ruby
# bad

hash = { food: 'apple', food: 'orange' }
```
```ruby
# good

hash = { food: 'apple', other_food: 'orange' }
```

## Further Reading

* [RuboCop - Lint/DuplicatedKey](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintduplicatedkey)
