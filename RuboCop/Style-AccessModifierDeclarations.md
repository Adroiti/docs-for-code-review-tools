Pattern: Malformed access modifier declaration

Issue: -

## Description

Access modifiers should be declared to apply to a group of methods or inline before each method, depending on configuration.

## Examples

#### EnforcedStyle: group (default)

```ruby
# bad

class Foo

  private def bar; end
  private def baz; end

end

# good

class Foo

  private

  def bar; end
  def baz; end

end
```
#### EnforcedStyle: inline

```ruby
# bad

class Foo

  private

  def bar; end
  def baz; end

end

# good

class Foo

  private def bar; end
  private def baz; end

end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | `group`

## Further Reading

* [RuboCop - Style/AccessModifierDeclarations](https://docs.rubocop.org/rubocop/cops_style.html#styleaccessmodifierdeclarations)
