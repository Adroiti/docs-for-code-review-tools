Pattern: Use of Rails `setup` method

Issue: -

## Description

Checks that tests use RSpec `before` hook over Rails `setup` method.

## Examples

```ruby
# bad
setup do
  allow(foo).to receive(:bar)
end

# good
before do
  allow(foo).to receive(:bar)
end
```

## Further Reading

* [RSpec/Rails/AvoidSetupHook](https://docs.rubocop.org/rubocop-rspec_rails/cops_rspecrails.html#rspecrailsavoidsetuphook)
