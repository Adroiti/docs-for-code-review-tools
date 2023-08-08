Pattern: Malformed `)` indentation

Issue: -

## Description

This rule checks the indentation of hanging closing parentheses in
method calls, method definitions, and grouped expressions. A hanging
closing parenthesis means `)` preceded by a line break.

## Examples

```ruby
# good: when x is on its own line, indent this way
func(
  x,
  y
)

# good: when x follows opening parenthesis, align parentheses
a = b * (x +
         y
        )

# bad
def func(
  x,
  y
  )
```

## Further Reading

* [RuboCop - Layout/ClosingParenthesisIndentation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutclosingparenthesisindentation)
