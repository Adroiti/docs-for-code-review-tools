Pattern: Message expectation with configured response

Issue: -

## Description

Checks that message expectations do not have a configured response.

## Examples

```ruby
# bad
expect(foo).to receive(:bar).with(42).and_return("hello world")

# good (without spies)
allow(foo).to receive(:bar).with(42).and_return("hello world")
expect(foo).to receive(:bar).with(42)
```

## Further Reading

* [RSpec - RSpec/StubbedMock](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecstubbedmock)