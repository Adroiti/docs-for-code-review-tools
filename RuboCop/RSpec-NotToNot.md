Pattern: Inconsistent method use for negating expectation

Issue: -

## Description

Checks for consistent method usage for negating expectations.

## Examples

```ruby
# bad
it '...' do
  expect(false).to_not be_true
end

# good
it '...' do
  expect(false).not_to be_true
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `not_to` | `not_to`, `to_not`

## Further Reading

* [RSpec - RSpec/NotToNot](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecnottonot)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NotToNot](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NotToNot)
