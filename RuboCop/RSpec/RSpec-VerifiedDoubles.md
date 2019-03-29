Pattern: Missing use of verifying double

Issue: -

## Description

Prefer using verifying doubles over normal doubles.

## Examples

```ruby
# bad
let(:foo) do
  double(method_name: 'returned value')
end

# bad
let(:foo) do
  double("ClassName", method_name: 'returned value')
end

# good
let(:foo) do
  instance_double("ClassName", method_name: 'returned value')
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
IgnoreNameless | `true` | Boolean
IgnoreSymbolicNames | `false` | Boolean

## Further Reading

* [RSpec - RSpec/VerifiedDoubles](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecverifieddoubles)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VerifiedDoubles](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VerifiedDoubles)
