Pattern: Wrong condition position

Issue: -

## Description

This cop checks for conditions that are not on the same line as `if`/`while`/`until`.

### Example

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

* [RuboCop - Lint/ConditionPosition](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintconditionposition)
* [https://github.com/bbatsov/ruby-style-guide#same-line-condition](https://github.com/bbatsov/ruby-style-guide#same-line-condition)
