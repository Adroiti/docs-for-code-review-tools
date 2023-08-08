Pattern: Wrong mixin grouping

Issue: -

## Description

This rule checks for grouping of mixins in `class` and `module` bodies.
By default it enforces mixins to be placed in separate declarations,
but it can be configured to enforce grouping them in one declaration.

## Examples

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

* [RuboCop - Style/MixinGrouping](https://docs.rubocop.org/rubocop/cops_style.html#stylemixingrouping)
* [https://github.com/bbatsov/ruby-style-guide#mixin-grouping](https://github.com/bbatsov/ruby-style-guide#mixin-grouping)
