Pattern: Layout/FirstMethodArgumentLineBreak

Issue: -

## Description

This cop checks for a line break before the first argument in a
multi-line method call.

### Example

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

* [RuboCop - Layout/FirstMethodArgumentLineBreak](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutfirstmethodargumentlinebreak)
