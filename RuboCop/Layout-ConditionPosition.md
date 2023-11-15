Pattern: Wrong condition position

Issue: -

## Description

This rule checks for conditions that are not on the same line as `if`/`while`/`until`.

## Examples

```ruby
# bad

if
  some_condition
  do_something
end
```
```ruby
# good

if some_condition
  do_something
end
```

## Further Reading

* [RuboCop - Layout/ConditionPosition](https://docs.rubocop.org/rubocop/cops_layout.html#layoutconditionposition)
* [https://github.com/bbatsov/ruby-style-guide#same-line-condition](https://github.com/bbatsov/ruby-style-guide#same-line-condition)
