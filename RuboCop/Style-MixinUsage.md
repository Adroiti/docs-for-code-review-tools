Pattern: Statement usage at the top level

Issue: -

## Description

This rule checks if `include`, `extend` and `prepend` exists at the top level. Using these at the top level affects the behavior of `Object`.

## Examples

```ruby
# bad
include M

class C
end

# bad
extend M

class C
end

# bad
prepend M

class C
end

# good
class C
  include M
end

# good
class C
  extend M
end

# good
class C
  prepend M
end
```

## Further Reading

* [RuboCop - Style/MixinUsage](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemixinusage)
