Pattern: RSpec example without expectation

Issue: -

## Description

Checks if an example contains any expectation.

All RSpec's example and expectation methods are covered by default.
If you are using your own custom methods,
add the following configuration:

  RSpec:
    Language:
      Examples:
        Regular:
          - custom_it
      Expectations:
        - custom_expect

## Examples

```ruby
# bad
it do
  a?
end

# good
it do
  expect(a?).to be(true)
end
```

## Further Reading

* [RSpec - RSpec/NoExpectationExample](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecnoexpectationexample)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NoExpectationExample