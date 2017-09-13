Pattern: Lint/DuplicatedKey

Issue: -

## Description

This cop checks for duplicated keys in hash literals.

This cop mirrors a warning in Ruby 2.2.

### Example

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
