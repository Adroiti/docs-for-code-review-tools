Pattern: Missing explicit visibility for constant

Issue: -

## Description

By default, Ruby makes all class and module constants public, which litters the public API of the class or module. Explicitly declaring a visibility makes intent more clear, and prevents outside actors from touching private state.

### Examples

```ruby
# bad
class Test
  BAR = 42
  BAZ = 43
end

# good
class Test
  BAR = 42
  private_constant :BAR

  BAZ = 43
  public_constant :BAZ
end
```

## Further Reading

* [RuboCop - Style/ConstantVisibility](https://docs.rubocop.org/rubocop/cops_style.html#styleconstantvisibility)
