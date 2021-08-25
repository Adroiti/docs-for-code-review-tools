Pattern: Malformed second argument to `describe`

Issue: -

## Description

Checks that the second argument to `describe` specifies a method.

## Examples

```ruby
# bad
describe MyClass, 'do something' do
end

# good
describe MyClass, '#my_instance_method' do
end

describe MyClass, '.my_class_method' do
end
```

## Further Reading

* [RSpec - RSpec/DescribeMethod](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecdescribemethod)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribeMethod](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribeMethod)
