Pattern: Use of `Array#*`

Issue: -

## Description

This rule checks for uses of fairly cryptic `Array#*` to be replaced with `Array#join`.

Not all cases can reliably checked, due to Ruby's dynamic types, so it considers only cases when the first argument is an array literal or the second is a string literal.

## Examples

```ruby
# bad
%w[one two three] * ', '
# => 'one, two, three'

# good
%w[one two three].join(', ')
# => 'one, two, three'
```

## Further Reading

* [RuboCop - Style/ArrayJoin](https://docs.rubocop.org/rubocop/cops_style.html#stylearrayjoin)
* [https://github.com/bbatsov/ruby-style-guide#array-join](https://github.com/bbatsov/ruby-style-guide#array-join)
