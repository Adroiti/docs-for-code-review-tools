Pattern: Use of globally stubbed instance

Issue: -

## Description

Checks that instances are not being stubbed globally.

Prefer instance doubles over stubbing any instance of a class

## Examples

```ruby
# bad
describe MyClass do
  before { allow_any_instance_of(MyClass).to receive(:foo) }
end

# good
describe MyClass do
  let(:my_instance) { instance_double(MyClass) }

  before do
    allow(MyClass).to receive(:new).and_return(my_instance)
    allow(my_instance).to receive(:foo)
  end
end
```

## Further Reading

* [RSpec - RSpec/AnyInstance](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecanyinstance)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AnyInstance](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AnyInstance)
