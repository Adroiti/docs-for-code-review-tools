Pattern: `_` for used variable

Issue: -

## Description

This rule checks for underscore-prefixed variables that are actually used.

## Examples

```ruby
# bad

[1, 2, 3].each do |_num|
  do_something(_num)
end
```
```ruby
# good

[1, 2, 3].each do |num|
  do_something(num)
end
```
```ruby
# good

[1, 2, 3].each do |_num|
  do_something # not using `_num`
end
```

## Further Reading

* [RuboCop - Lint/UnderscorePrefixedVariableName](https://docs.rubocop.org/rubocop/cops_lint.html#lintunderscoreprefixedvariablename)
