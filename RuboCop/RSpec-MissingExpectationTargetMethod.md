Pattern: Missing use of `.to`/`not_to`/`to_not`

Issue: -

## Description

Checks if `.to`, `not_to` or `to_not` are used.

## Examples

```ruby
# bad
expect(something).kind_of? Foo
is_expected == 42
expect{something}.eq? BarError

# good
expect(something).to be_a Foo
is_expected.to eq 42
expect{something}.to raise_error BarError
```

## Further Reading

* [RSpec - MissingExpectationTargetMethod](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmissingexpectationtargetmethod)
