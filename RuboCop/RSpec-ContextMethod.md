Pattern: Method name in `context`

Issue: -

## Description

`context` should not be used for specifying methods.

## Examples

```ruby
# bad
context '#foo_bar' do
  # ...
end

context '.foo_bar' do
  # ...
end

# good
describe '#foo_bar' do
  # ...
end

describe '.foo_bar' do
  # ...
end
```

## Further Reading

* [RSpec - RSpec/ContextMethod](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspeccontextmethod)
