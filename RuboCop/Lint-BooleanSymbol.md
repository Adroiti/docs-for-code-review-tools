Pattern: Use of `:true`/`:false`

Issue: -

## Description

This cop checks for `:true` and `:false` symbols. In most cases it would be a typo.

### Example

```ruby
# bad
:true

# good
true
```
```ruby
# bad
:false

# good
false
```

## Further Reading

* [RuboCop - Lint/BooleanSymbol](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintbooleansymbol)
