Pattern: Use of `each` for simple loop

Issue: -

## Description

This rule checks for loops which iterate a constant number of times,
using a Range literal and `#each`. This can be done more readably using `Integer#times`.

This check only applies if the block takes no parameters.

## Examples

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

* [RuboCop - Style/EachForSimpleLoop](https://docs.rubocop.org/rubocop/cops_style.html#styleeachforsimpleloop)
