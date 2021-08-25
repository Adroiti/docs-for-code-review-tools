Pattern: Inconsistent message expectation

Issue: -

## Description

Checks for consistent message expectation style.

This rule can be configured in your configuration using the `EnforcedStyle` option.

## Examples

#### `EnforcedStyle: allow`

```ruby
# bad
expect(foo).to receive(:bar)

# good
allow(foo).to receive(:bar)
```
#### `EnforcedStyle: expect`

```ruby
# bad
allow(foo).to receive(:bar)

# good
expect(foo).to receive(:bar)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `allow` | `allow`, `expect`

## Further Reading

* [RSpec - RSpec/MessageExpectation](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmessageexpectation)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MessageExpectation](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MessageExpectation)
