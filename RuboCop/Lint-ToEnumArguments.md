Pattern: Wrong arguments for `to_enum`/`enum_for`

Issue: -

## Description

Ensures that `to_enum`/`enum_for`, called for the current method, has correct arguments.

## Examples

```ruby
# bad
def method(x, y = 1)
  return to_enum(__method__, x) # `y` is missing
end

# good
def method(x, y = 1)
  return to_enum(__method__, x, y)
end

# bad
def method(required:)
  return to_enum(:method, required: something) # `required` has incorrect value
end

# good
def method(required:)
  return to_enum(:method, required: required)
end
```

## Further Reading

* [RuboCop - Lint/ToEnumArguments](https://docs.rubocop.org/rubocop/cops_lint.html#linttoenumarguments)
