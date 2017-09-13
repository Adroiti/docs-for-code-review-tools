Pattern: Lint/AmbiguousBlockAssociation

Issue: -

## Description

This cop checks for ambiguous block association with method
when param passed without parentheses.

### Example

```ruby
# bad
some_method a { |val| puts val }
```
```ruby
# good
# With parentheses, there's no ambiguity.
some_method(a) { |val| puts val }

# good
# Operator methods require no disambiguation
foo == bar { |b| b.baz }

# good
# Lambda arguments require no disambiguation
foo = ->(bar) { bar.baz }
```

## Further Reading

* [RuboCop - Lint/AmbiguousBlockAssociation](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintambiguousblockassociation)
* [https://github.com/bbatsov/ruby-style-guide#syntax](https://github.com/bbatsov/ruby-style-guide#syntax)
