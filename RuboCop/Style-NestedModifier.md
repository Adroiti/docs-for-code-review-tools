Pattern: Use of nested modifier

Issue: -

## Description

This rule checks for nested use of `if`, `unless`, `while` and `until` in their modifier form. Use `&&`/`||` if appropriate.

## Examples

```ruby
# bad
something if a if b

# good
something if b && a
```

## Further Reading

* [RuboCop - Style/NestedModifier](https://docs.rubocop.org/rubocop/cops_style.html#stylenestedmodifier)
* [https://github.com/bbatsov/ruby-style-guide#no-nested-modifiers](https://github.com/bbatsov/ruby-style-guide#no-nested-modifiers)
