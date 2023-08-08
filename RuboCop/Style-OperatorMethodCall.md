Pattern: Redundant `.` before operator

Issue: -

## Description

Checks for redundant dot before operator method call.

The target operator methods are `|`, `^`, `&`, `<=>`, `==`, `===`, `=~`, `>`, `>=`, `<`, `<=`, `<<`, `>>`, `+`, `-`, `*`, `/`, `%`, `**`, `~`, `!`, `!=`, and `!~`.

## Examples

```ruby
# bad
foo.+ bar
foo.& bar

# good
foo + bar
foo & bar
```

## Further Reading

* [RuboCop - Style/OperatorMethodCall](https://docs.rubocop.org/rubocop/cops_style.html#styleoperatormethodcall)
