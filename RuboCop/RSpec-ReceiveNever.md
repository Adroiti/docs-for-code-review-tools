Pattern: Use of `receive(...).never` instead of `not_to receive(...)`

Issue: -

## Description

Prefer `not_to receive(...)` over `receive(...).never`.

## Examples

```ruby
# bad
expect(foo).to receive(:bar).never

# good
expect(foo).not_to receive(:bar)
```

## Further Reading

* [RSpec - RSpec/ReceiveNever](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecreceivenever)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ReceiveNever](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ReceiveNever)
