Pattern: Unused ternary operator (`?:`) on single line

Issue: -

## Description

Ternary operator(`?:`) is more common and more concise than `if`/`then`/`else`/`end` constructs.

### Example

```ruby
# bad
result = if some_condition then something else something_else end

# good
result = some_condition ? something : something_else
```

## Further Reading

* [RuboCop - Style/OneLineConditional](https://rubocop.readthedocs.io/en/latest/cops_style/#styleonelineconditional)
* [https://github.com/bbatsov/ruby-style-guide#ternary-operator](https://github.com/bbatsov/ruby-style-guide#ternary-operator)
