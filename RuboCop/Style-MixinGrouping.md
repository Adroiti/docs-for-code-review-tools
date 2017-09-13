Pattern: Style/MixinGrouping

Issue: -

## Description

This cop checks for grouping of mixins in `class` and `module` bodies.
By default it enforces mixins to be placed in separate declarations,
but it can be configured to enforce grouping them in one declaration.

### Example

```ruby
EnforcedStyle: separated (default)

# bad
class Foo
  include Bar, Qox
end

# good
class Foo
  include Qox
  include Bar
end

EnforcedStyle: grouped

# bad
class Foo
  extend Bar
  extend Qox
end

# good
class Foo
  extend Qox, Bar
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | separated
SupportedStyles | separated, grouped

## Further Reading

* [RuboCop - Style/MixinGrouping](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemixingrouping)
* [https://github.com/bbatsov/ruby-style-guide#mixin-grouping](https://github.com/bbatsov/ruby-style-guide#mixin-grouping)
