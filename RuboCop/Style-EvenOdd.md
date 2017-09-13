Pattern: Style/EvenOdd

Issue: -

## Description

This cop checks for places where Integer#even? or Integer#odd?
should have been used.

### Example

```ruby
# bad
if x % 2 == 0

# good
if x.even?
```

## Further Reading

* [RuboCop - Style/EvenOdd](https://rubocop.readthedocs.io/en/latest/cops_style/#styleevenodd)
* [https://github.com/bbatsov/ruby-style-guide#predicate-methods](https://github.com/bbatsov/ruby-style-guide#predicate-methods)
