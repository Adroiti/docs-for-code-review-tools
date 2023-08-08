Pattern: Missing use of value swapping

Issue: -

## Description

Enforces the use of shorthand-style swapping of 2 variables. Its autocorrection is marked as unsafe, because it can erroneously remove the temporary variable which is used later.

## Examples

```ruby
# bad
tmp = x
x = y
y = tmp

# good
x, y = y, x
```

## Further Reading

* [RuboCop - Style/SwapValues](https://docs.rubocop.org/rubocop/cops_style.html#styleswapvalues)
