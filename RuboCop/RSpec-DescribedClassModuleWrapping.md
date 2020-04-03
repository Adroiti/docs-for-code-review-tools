Pattern: Opening module and defining spec within

Issue: -

## Description

Avoid opening modules and defining specs within them.

## Examples

```ruby
# bad
module MyModule
  RSpec.describe MyClass do
    # ...
  end
end

# good
RSpec.describe MyModule::MyClass do
  # ...
end
```

## Further Reading

* [RSpec - RSpec/DescribedClassModuleWrapping](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecdescribedclassmodulewrapping)
