Pattern: Missing use of `if`/`unless`

Issue: -

## Description

Checks for `if` and `unless` statements that would fit on one line if written as a modifier `if`/`unless`. The maximum line length is configurable.

## Examples

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

* [RuboCop - Style/IfUnlessModifier](https://docs.rubocop.org/rubocop/cops_style.html#styleifunlessmodifier)
* [https://github.com/bbatsov/ruby-style-guide#if-as-a-modifier](https://github.com/bbatsov/ruby-style-guide#if-as-a-modifier)
