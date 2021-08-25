Pattern: Inconsistent implicit expectation

Issue: -

## Description

Checks that a consistent implicit expectation style is used.

This rule can be configured using the `EnforcedStyle` option.

## Examples

#### `EnforcedStyle: is_expected`

```ruby
# bad
it { should be_truthy }

# good
it { is_expected.to be_truthy }
```
#### `EnforcedStyle: should`

```ruby
# bad
it { is_expected.to be_truthy }

# good
it { should be_truthy }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `is_expected` | `is_expected`, `should`

## Further Reading

* [RSpec - RSpec/ImplicitExpect](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecimplicitexpect)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ImplicitExpect](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ImplicitExpect)
