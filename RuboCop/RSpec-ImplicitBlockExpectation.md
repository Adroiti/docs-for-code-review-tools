Pattern: Implicit block expectation

Issue: -

## Description

Checks that implicit block expectation syntax is not used. Prefer using explicit block expectations.

## Examples

```ruby
# bad
subject { -> { do_something } }
it { is_expected.to change(something).to(new_value) }

# good
it 'changes something to a new value' do
  expect { do_something }.to change(something).to(new_value)
end
```

## Further Reading

* [RSpec - RSpec/ImplicitBlockExpectation](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecimplicitblockexpectation)
