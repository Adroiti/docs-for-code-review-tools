Pattern: Empty expression

Issue: -

## Description

This rule checks for the presence of empty expressions.

## Examples

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

* [RuboCop - Lint/EmptyExpression](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyexpression)
