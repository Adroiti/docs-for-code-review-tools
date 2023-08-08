Pattern: Use of `:true`/`:false`

Issue: -

## Description

This rule checks for `:true` and `:false` symbols. In most cases it would be a typo.

## Examples

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

* [RuboCop - Lint/BooleanSymbol](https://docs.rubocop.org/rubocop/cops_lint.html#lintbooleansymbol)
