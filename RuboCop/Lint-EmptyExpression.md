Pattern: Empty expression

Issue: -

## Description

This cop checks for the presence of empty expressions.

### Example

```ruby
# bad

foo = ()
if ()
  bar
end
```
```ruby
# good

foo = (some_expression)
if (some_expression)
  bar
end
```

## Further Reading

* [RuboCop - Lint/EmptyExpression](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintemptyexpression)
