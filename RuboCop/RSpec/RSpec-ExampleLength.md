Pattern: Long example

Issue: -

## Description

Checks for long examples.

A long example is usually more difficult to understand. Consider
extracting out some behavior, e.g. with a `let` block, or a helper
method.

## Examples

```ruby
# bad
it do
  service = described_class.new
  more_setup
  more_setup
  result = service.call
  expect(result).to be(true)
end

# good
it do
  service = described_class.new
  result = service.call
  expect(result).to be(true)
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `5` | Integer

## Further Reading

* [RSpec - RSpec/ExampleLength](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecexamplelength)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExampleLength](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExampleLength)
