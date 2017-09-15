Pattern: Missing line break before first method parameter

Issue: -

## Description

This cop checks for a line break before the first parameter in a multi-line method parameter definition.

### Example

```ruby
# bad
def method(foo, bar,
    baz)
  do_something
end

# good
def method(
    foo, bar,
    baz)
  do_something
end

# ignored
def method foo,
    bar
  do_something
end
```

## Further Reading

* [RuboCop - Layout/FirstMethodParameterLineBreak](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutfirstmethodparameterlinebreak)
