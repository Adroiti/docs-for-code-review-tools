Pattern: Inconsistent return from stub

Issue: -

## Description

Checks for consistent style of stub's return setting.

Enforces either `and_return` or block-style return in the cases
where the returned value is constant. Ignores dynamic returned values
are the result would be different

This rule can be configured using the `EnforcedStyle` option

## Examples

#### `EnforcedStyle: block`

```ruby
# bad
allow(Foo).to receive(:bar).and_return("baz")
expect(Foo).to receive(:bar).and_return("baz")

# good
allow(Foo).to receive(:bar) { "baz" }
expect(Foo).to receive(:bar) { "baz" }
# also good as the returned value is dynamic
allow(Foo).to receive(:bar).and_return(bar.baz)
```
#### `EnforcedStyle: and_return`

```ruby
# bad
allow(Foo).to receive(:bar) { "baz" }
expect(Foo).to receive(:bar) { "baz" }

# good
allow(Foo).to receive(:bar).and_return("baz")
expect(Foo).to receive(:bar).and_return("baz")
# also good as the returned value is dynamic
allow(Foo).to receive(:bar) { bar.baz }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `and_return` | `and_return`, `block`

## Further Reading

* [RSpec - RSpec/ReturnFromStub](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecreturnfromstub)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ReturnFromStub](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ReturnFromStub)
