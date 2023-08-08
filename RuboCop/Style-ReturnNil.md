Pattern: Inconsistent use of `return nil`/`return`

Issue: -

## Description

This rule enforces consistency between `return nil` and `return`.

## Examples

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

* [RuboCop - Style/ReturnNil](https://docs.rubocop.org/rubocop/cops_style.html#stylereturnnil)
