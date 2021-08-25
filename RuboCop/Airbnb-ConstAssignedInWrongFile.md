Pattern: Const assigned in wronf file

Issue: -

## Description

Checks for a constant assigned in a file that does not match its owning scope. The Rails autoloader can't find such a constant, but sometimes people "get lucky" if the file happened to be loaded before the method was defined.

## Examples

```ruby
# bad

# foo/bar.rb
module Foo
  BAZ = 42
end

# good

# foo.rb
module Foo
  BAZ = 42
end
```

## Further Reading

* [RuboCop - Airbnb/ConstAssignedInWrongFile](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/const_assigned_in_wrong_file.rb)
