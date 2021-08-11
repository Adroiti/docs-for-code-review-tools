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

* [RSpec - RSpec/ContextMethod](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspeccontextmethod)
