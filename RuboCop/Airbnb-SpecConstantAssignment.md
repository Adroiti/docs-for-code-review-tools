Pattern: Constant assignment in pec

Issue: -

## Description

Checks for constant assignment inside of specs.

## Examples

```ruby
# bad
describe Something do
  PAYLOAD = [1, 2, 3]
end

# good
describe Something do
  let(:payload)  { [1, 2, 3] }
end

# bad
describe Something do
  MyClass::PAYLOAD = [1, 2, 3]
end

# good
describe Something do
  before { stub_const('MyClass::PAYLOAD', [1, 2, 3])
end
```

## Further Reading

* [RuboCop - Airbnb/SpecConstantAssignment](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/spec_constant_assignment.rb)
