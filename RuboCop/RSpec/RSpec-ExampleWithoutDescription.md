Pattern: Example without description

Issue: -

## Description

Checks for examples without a description.

RSpec allows for auto-generated example descriptions when there is no description provided or the description is an empty one.

This rule removes empty descriptions. It also defines whether auto-generated description is allowed, based on the configured style. This rule can be configured using the `EnforcedStyle` option

## Examples

#### `EnforcedStyle: always_allow`

```ruby
# bad
it('') { is_expected.to be_good }
it '' do
  result = service.call
  expect(result).to be(true)
end

# good
it { is_expected.to be_good }
it do
  result = service.call
  expect(result).to be(true)
end
```
#### `EnforcedStyle: single_line_only`

```ruby
# bad
it('') { is_expected.to be_good }
it do
  result = service.call
  expect(result).to be(true)
end

# good
it { is_expected.to be_good }
```
#### `EnforcedStyle: disallow`

```ruby
# bad
it { is_expected.to be_good }
it do
  result = service.call
  expect(result).to be(true)
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `always_allow` | `always_allow`, `single_line_only`, `disallow`

## Further Reading

* [RSpec - RSpec/ExampleWithoutDescription](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecexamplewithoutdescription)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExampleWithoutDescription](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExampleWithoutDescription)
