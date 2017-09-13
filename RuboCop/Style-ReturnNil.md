Pattern: Style/ReturnNil

Issue: -

## Description

This cop enforces consistency between 'return nil' and 'return'.

Supported styles are: return, return_nil.

### Example

```ruby
# EnforcedStyle: return (default)

# bad
def foo(arg)
  return nil if arg
end

# good
def foo(arg)
  return if arg
end

# EnforcedStyle: return_nil

# bad
def foo(arg)
  return if arg
end

# good
def foo(arg)
  return nil if arg
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | return
SupportedStyles | return, return_nil

## Further Reading

* [RuboCop - Style/ReturnNil](https://rubocop.readthedocs.io/en/latest/cops_style/#stylereturnnil)
