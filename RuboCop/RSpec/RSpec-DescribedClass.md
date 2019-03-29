Pattern: Malformed `described_class`

Issue: -

## Description

Checks that tests use `described_class`. If the first argument of describe is a class, the class is exposed to each example via `described_class`.

This rule can be configured using the `EnforcedStyle` option

## Examples

#### `EnforcedStyle: described_class`

```ruby
# bad
describe MyClass do
  subject { MyClass.do_something }
end

# good
describe MyClass do
  subject { described_class.do_something }
end
```
#### `EnforcedStyle: explicit`

```ruby
# bad
describe MyClass do
  subject { described_class.do_something }
end

# good
describe MyClass do
  subject { MyClass.do_something }
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
SkipBlocks | `false` | Boolean
EnforcedStyle | `described_class` | `described_class`, `explicit`

## Further Reading

* [RSpec - RSpec/DescribedClass](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecdescribedclass)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribedClass](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribedClass)
