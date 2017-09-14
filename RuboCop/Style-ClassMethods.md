Pattern: Class methods

Issue: -

## Description

This cop checks for uses of the class/module name instead of
self, when defining class/module methods.

### Example

```ruby
# bad
class SomeClass
  def SomeClass.class_method
    ...
  end
end

# good
class SomeClass
  def self.class_method
    ...
  end
end
```

## Further Reading

* [RuboCop - Style/ClassMethods](https://rubocop.readthedocs.io/en/latest/cops_style/#styleclassmethods)
* [https://github.com/bbatsov/ruby-style-guide#def-self-class-methods](https://github.com/bbatsov/ruby-style-guide#def-self-class-methods)
