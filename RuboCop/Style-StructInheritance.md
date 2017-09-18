Pattern: Inheritance from `Struct.new`

Issue: -

## Description

This rule checks for inheritance from `Struct.new`. Extending it introduces a superfluous class level and may also introduce weird errors if the file is required multiple times.

## Examples

```ruby
# bad
class Person < Struct.new(:first_name, :last_name)
end

# good
Person = Struct.new(:first_name, :last_name)
```

## Further Reading

* [RuboCop - Style/StructInheritance](https://rubocop.readthedocs.io/en/latest/cops_style/#stylestructinheritance)
* [https://github.com/bbatsov/ruby-style-guide#no-extend-struct-new](https://github.com/bbatsov/ruby-style-guide#no-extend-struct-new)
