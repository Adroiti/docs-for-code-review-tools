Pattern: Use of nested modifier

Issue: -

## Description

This cop checks for nested use of `if`, `unless`, `while` and `until` in their modifier form. Use `&&`/`||` if appropriate.

### Example

```ruby
# bad
something if a if b

# good
something if b && a
```

## Further Reading

* [RuboCop - Style/NestedModifier](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenestedmodifier)
* [https://github.com/bbatsov/ruby-style-guide#no-nested-modifiers](https://github.com/bbatsov/ruby-style-guide#no-nested-modifiers)
