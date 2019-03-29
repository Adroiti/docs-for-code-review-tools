Pattern: Multiple top level descriptions

Issue: -

## Description

Checks for multiple top level `describe`s.

Multiple descriptions for the same class or module should either be nested or separated into different test files.

## Examples

```ruby
# bad
describe MyClass, '.do_something' do
end
describe MyClass, '.do_something_else' do
end

# good
describe MyClass do
  describe '.do_something' do
  end
  describe '.do_something_else' do
  end
end
```

## Further Reading

* [RSpec - RSpec/MultipleDescribes](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecmultipledescribes)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MultipleDescribes](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MultipleDescribes)
