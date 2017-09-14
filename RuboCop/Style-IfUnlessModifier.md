Pattern: Unused `if`/`unless` for single-line body

Issue: -

## Description

Checks for `if` and `unless` statements that would fit on one line if written as a modifier `if`/`unless`. The maximum line length is configurable.

### Example

```ruby
# bad
if some_condition
  do_something
end

# good
do_something if some_condition
```

## Default configuration

Attribute | Value
--- | ---
MaxLineLength | 80

## Further Reading

* [RuboCop - Style/IfUnlessModifier](https://rubocop.readthedocs.io/en/latest/cops_style/#styleifunlessmodifier)
* [https://github.com/bbatsov/ruby-style-guide#if-as-a-modifier](https://github.com/bbatsov/ruby-style-guide#if-as-a-modifier)
