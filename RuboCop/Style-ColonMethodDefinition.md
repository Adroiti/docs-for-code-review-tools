Pattern: Use of `::` for defining class method

Issue: -

## Description

This rule checks for class methods that are defined using the `::` operator instead of the `.` operator.

## Examples

```ruby
# bad
class Foo
  def self::bar
  end
end

# good
class Foo
  def self.bar
  end
end
```

## Further Reading

* [RuboCop - Style/ColonMethodDefinition](https://docs.rubocop.org/rubocop/cops_style.html#stylecolonmethoddefinition)
* [https://github.com/bbatsov/ruby-style-guide#colon-method-definition](https://github.com/bbatsov/ruby-style-guide#colon-method-definition)
