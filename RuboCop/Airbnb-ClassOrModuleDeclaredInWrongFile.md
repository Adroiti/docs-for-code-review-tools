Pattern: Class/module declared in wrong file

Issue: -

## Description

Checks for a class or module declared in a file that does not match its name. The Rails autoloader can't find such a constant, but sometimes people "get lucky" if the file happened to be loaded before the method was defined.

## Examples

```ruby
# bad

# foo/bar.rb
module Foo
  class Goop
  end

  module Moo
  end
end

# good

# foo.rb

# foo/goop.rb
module Foo
  class Goop
  end
end

# foo/moo.rb
module Foo
  module Moo
  end
end

Note that autoloading works fine if classes are defined in the file that defines
the module. This is common usage for things like error classes, so we'll allow it.
Nested classes are also allowed:

# good

# foo.rb
module Foo
  class Bar < StandardError
  end
end

# good

# foo.rb
class Foo
  class Bar # nested class
  end
end
```

## Further Reading

* [RuboCop - Airbnb/ClassOrModuleDeclaredInWrongFile](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/class_or_module_declared_in_wrong_file.rb)
