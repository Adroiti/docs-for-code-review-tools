Pattern: Missing use of `?:` on single line

Issue: -

## Description

Ternary operator(`?:`) is more common and more concise than `if`/`then`/`else`/`end` constructs.

## Examples

```ruby
# bad
result = if some_condition then something else something_else end

# good
result = some_condition ? something : something_else
```

## Further Reading

* [RuboCop - Style/OneLineConditional](https://docs.rubocop.org/rubocop/cops_style.html#styleonelineconditional)
* [https://github.com/bbatsov/ruby-style-guide#ternary-operator](https://github.com/bbatsov/ruby-style-guide#ternary-operator)
