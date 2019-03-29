Pattern: Missing actual for `expect(...)`

Issue: -

## Description

Checks for `expect(...)` calls containing literal values.

## Examples

```ruby
# bad
expect(5).to eq(price)
expect(/foo/).to eq(pattern)
expect("John").to eq(name)

# good
expect(price).to eq(5)
expect(pattern).to eq(/foo/)
expect(name).to eq("John")
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Exclude | `spec/routing/**/*` | Array

## Further Reading

* [RSpec - RSpec/ExpectActual](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecexpectactual)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectActual](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectActual)
