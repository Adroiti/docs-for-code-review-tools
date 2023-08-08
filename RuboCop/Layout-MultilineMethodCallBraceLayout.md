Pattern: Misaligned multi-line method call brace

Issue: -

## Description

This rule checks that the closing brace in a method call is either
on the same line as the last method argument, or a new line.

When using the `symmetrical` (default) style:

If a method call's opening brace is on the same line as the first
argument of the call, then the closing brace should be on the same
line as the last argument of the call.

If an method call's opening brace is on the line above the first
argument of the call, then the closing brace should be on the line
below the last argument of the call.

When using the `new_line` style:

The closing brace of a multi-line method call must be on the line
after the last argument of the call.

When using the `same_line` style:

The closing brace of a multi-line method call must be on the same
line as the last argument of the call.

## Examples

```ruby
# symmetrical: bad
# new_line: good
# same_line: bad
foo(a,
  b
)

# symmetrical: bad
# new_line: bad
# same_line: good
foo(
  a,
  b)

# symmetrical: good
# new_line: bad
# same_line: good
foo(a,
  b)

# symmetrical: good
# new_line: good
# same_line: bad
foo(
  a,
  b
)
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | symmetrical
SupportedStyles | symmetrical, new_line, same_line

## Further Reading

* [RuboCop - Layout/MultilineMethodCallBraceLayout](https://docs.rubocop.org/rubocop/cops_layout.html#layoutmultilinemethodcallbracelayout)
