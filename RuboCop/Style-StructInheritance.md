Pattern: Struct inheritance

Issue: -

## Description

This cop checks for inheritance from Struct.new.

### Example

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
