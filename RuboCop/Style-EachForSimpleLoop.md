Pattern: Use of `each` for simple loop

Issue: -

## Description

This cop checks for loops which iterate a constant number of times,
using a Range literal and `#each`. This can be done more readably using `Integer#times`.

This check only applies if the block takes no parameters.

### Example

```ruby
# bad
(1..5).each { }

# good
5.times { }
```
```ruby
# bad
(0...10).each {}

# good
10.times {}
```

## Further Reading

* [RuboCop - Style/EachForSimpleLoop](https://rubocop.readthedocs.io/en/latest/cops_style/#styleeachforsimpleloop)
