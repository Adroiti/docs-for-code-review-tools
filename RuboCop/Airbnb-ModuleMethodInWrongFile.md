Pattern: Module method in wrong file

Issue: -

## Description

Checks for methods defined in a module declaration, in a file that doesn't match the module name. The Rails autoloader can't find such a method, but sometimes people "get lucky" if the file happened to be loaded before the method was defined.

## Examples

```ruby
# bad

# foo/bar.rb
module Foo
  class Bar
  end

  def baz
    42
  end
end

# good

# foo/bar.rb
module Foo
  class Bar
  end
end

# foo.rb
module Foo
  def baz
    42
  end
end

Note that autoloading works fine if classes are defined in the file that defines
the module. This is common usage for things like error classes, so we'll allow it:


# good

# foo.rb
module Foo
  class Bar < StandardError
    def baz
    end
  end
end

# good

# foo.rb
class Foo
  class Bar # nested class
    def baz
    end
  end
end
```

## Further Reading

* [RuboCop - Airbnb/ModuleMethodInWrongFile](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/module_method_in_wrong_file.rb)
