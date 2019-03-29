Pattern: Use of implicit subject

Issue: -

## Description

Checks for usage of implicit subject (`is_expected`/`should`).

This rule can be configured using the `EnforcedStyle` option

## Examples

#### `EnforcedStyle: single_line_only`

```ruby
# bad
it do
  is_expected.to be_truthy
end

# good
it { is_expected.to be_truthy }
it do
  expect(subject).to be_truthy
end
```
#### `EnforcedStyle: disallow`

```ruby
# bad
it { is_expected.to be_truthy }

# good
it { expect(subject).to be_truthy }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `single_line_only` | `single_line_only`, `single_statement_only`, `disallow`

## Further Reading

* [RSpec - RSpec/ImplicitSubject](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecimplicitsubject)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ImplicitSubject](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ImplicitSubject)
