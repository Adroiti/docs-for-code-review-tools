Pattern: Malformed spec file path

Issue: -

## Description

Checks that spec file paths are consistent and well-formed.

## Examples

```ruby
# bad
whatever_spec.rb         # describe MyClass
my_class_spec.rb         # describe MyClass, '#method'

# good
my_class_spec.rb         # describe MyClass
my_class_method_spec.rb  # describe MyClass, '#method'
my_class/method_spec.rb  # describe MyClass, '#method'
```

## Further Reading

* [RSpec - RSpec/SpecFilePathFormat](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecspecfilepathformat)
