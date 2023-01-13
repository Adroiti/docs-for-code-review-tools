Pattern: Use of Yoda expression

Issue: -

## Description

Forbids Yoda expressions, i.e. binary operations (using `*`, `+`, `&`, `|`,
and `^` operators) where the order of expression is reversed, e.g. `1 + x`.
This rule complements `Style/YodaCondition` cop, which has a similar purpose.

This rule is disabled by default to respect user intentions such as:

```ruby
config.server_port = 9000 + ENV["TEST_ENV_NUMBER"].to_i
```

## Examples

#### SupportedOperators: ['*', '+', '&'']

```ruby
# bad
1 + x
10 * y
1 & z

# good
60 * 24
x + 1
y * 10
z & 1

# good
1 | x
```

## Further Reading

* [RuboCop - Style/YodaExpression](https://docs.rubocop.org/rubocop/cops_style.html#styleyodaexpression)
