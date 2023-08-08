Pattern: Missing use of `Integer#even?`/`Integer#odd?`

Issue: -

## Description

This rule checks for places where `Integer#even?` or `Integer#odd?` should have been used.

## Examples

```ruby
# bad
if x % 2 == 0

# good
if x.even?
```

## Further Reading

* [RuboCop - Style/EvenOdd](https://docs.rubocop.org/rubocop/cops_style.html#styleevenodd)
* [https://github.com/bbatsov/ruby-style-guide#predicate-methods](https://github.com/bbatsov/ruby-style-guide#predicate-methods)
