Pattern: Malformed indentation for access modifier

Issue: -

## Description

Modifiers should be indented as deep as method definitions, or as deep
as the `class`/`module` keyword, depending on configuration.

## Examples

```ruby
# EnforcedStyle: indent (default)

# bad
class Plumbus
private
  def smooth; end
end

# good
class Plumbus
  private
  def smooth; end
end

# EnforcedStyle: outdent

# bad
class Plumbus
  private
  def smooth; end
end

# good
class Plumbus
private
  def smooth; end
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | indent
SupportedStyles | outdent, indent
IndentationWidth |

## Further Reading

* [RuboCop - Layout/AccessModifierIndentation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutaccessmodifierindentation)
* [https://github.com/bbatsov/ruby-style-guide#indent-public-private-protected](https://github.com/bbatsov/ruby-style-guide#indent-public-private-protected)
