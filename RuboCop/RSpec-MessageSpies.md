Pattern: Missing spy use for message expectation

Issue: -

## Description

Checks that message expectations are set using spies.

This rule can be configured in your configuration using the `EnforcedStyle` option.

## Examples

#### `EnforcedStyle: have_received`

```ruby
# bad
expect(foo).to receive(:bar)

# good
expect(foo).to have_received(:bar)
```
#### `EnforcedStyle: receive`

```ruby
# bad
expect(foo).to have_received(:bar)

# good
expect(foo).to receive(:bar)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `have_received` | `have_received`, `receive`

## Further Reading

* [RSpec - RSpec/MessageSpies](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmessagespies)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MessageSpies](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MessageSpies)
