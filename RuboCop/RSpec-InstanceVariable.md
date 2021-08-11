Pattern: Misused instance variable in spec

Issue: -

## Description

Checks for instance variable usage in specs.

This rule can be configured with the option `AssignmentOnly` which
will configure the rule to only register offenses on instance
variable usage if the instance variable is also assigned within
the spec

## Examples

```ruby
# bad
describe MyClass do
  before { @foo = [] }
  it { expect(@foo).to be_empty }
end

# good
describe MyClass do
  let(:foo) { [] }
  it { expect(foo).to be_empty }
end
```
#### with AssignmentOnly configuration

```ruby
# rubocop.yml
# RSpec/InstanceVariable:
#   AssignmentOnly: false

# bad
describe MyClass do
  before { @foo = [] }
  it { expect(@foo).to be_empty }
end

# allowed
describe MyClass do
  it { expect(@foo).to be_empty }
end

# good
describe MyClass do
  let(:foo) { [] }
  it { expect(foo).to be_empty }
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AssignmentOnly | `false` | Boolean

## Further Reading

* [RSpec - RSpec/InstanceVariable](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecinstancevariable)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/InstanceVariable](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/InstanceVariable)
