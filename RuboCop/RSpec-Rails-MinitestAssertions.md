Pattern: Use of Minitest matcher

Issue: -

## Description

Check if using Minitest matchers.

## Examples

```ruby
# bad
assert_equal(a, b)
assert_equal a, b, "must be equal"
refute_equal(a, b)

# good
expect(a).to eq(b)
expect(a).to(eq(b), "must be equal")
expect(a).not_to eq(b)
```

## Further Reading

* [RSpec/Rails/MinitestAssertions](https://docs.rubocop.org/rubocop-rspec_rails/cops_rspecrails.html#rspecrailsminitestassertions)