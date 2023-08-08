Pattern: `while` with negated condition

Issue: -

## Description

Checks for uses of `while` with a negated condition. Use `until` instead.

## Examples

```ruby
# bad
do_something while !some_condition

# good
do_something until some_condition
```

## Further Reading

* [RuboCop - Style/NegatedWhile](https://docs.rubocop.org/rubocop/cops_style.html#stylenegatedwhile)
* [https://github.com/bbatsov/ruby-style-guide#until-for-negatives](https://github.com/bbatsov/ruby-style-guide#until-for-negatives)
