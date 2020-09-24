Pattern: Use of trailing comma in attribute declaration

Issue: -

## Description

This rule checks for trailing commas in attribute declarations, such as
`#attr_reader`. Leaving a trailing comma will nullify the next method
definition by overriding it with a getter method.

## Examples

```ruby
# bad
class Foo
  attr_reader :foo,

  def bar
    puts "Unreachable."
  end
end

# good
class Foo
  attr_reader :foo

  def bar
    puts "No problem!"
  end
end
```

## Further Reading

* [RuboCop - Lint/TrailingCommaInAttributeDeclaration](https://docs.rubocop.org/rubocop/cops_lint.html#linttrailingcommainattributedeclaration)
