Pattern: Missing line break before first method argument

Issue: -

## Description

This rule checks for a line break before the first argument in a multi-line method call.

## Examples

```ruby
# bad
method(foo, bar,
  baz)

# good
method(
  foo, bar,
  baz)

# ignored
method foo, bar,
  baz
```

## Further Reading

* [RuboCop - Layout/FirstMethodArgumentLineBreak](https://docs.rubocop.org/rubocop/cops_layout.html#layoutfirstmethodargumentlinebreak)
