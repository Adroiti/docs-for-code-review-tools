Pattern: Missing use of `self` for `class`/`module` method

Issue: -

## Description

This rule checks for uses of `self` when defining `class`/`module` methods. This makes the code easier to refactor since the class name is not repeated.

## Examples

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
