Pattern: Identical expressions on both sides of equality

Issue: -

## Description

Checks for equality assertions with identical expressions on both sides.

## Examples

```ruby
# bad
expect(foo.bar).to eq(foo.bar)
expect(foo.bar).to eql(foo.bar)

# good
expect(foo.bar).to eq(2)
expect(foo.bar).to eql(2)
```

## Further Reading

* [RSpec - RSpec/IdenticalEqualityAssertion](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecidenticalequalityassertion)
