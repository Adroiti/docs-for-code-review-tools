Pattern: Multiple messages stubbed on the same object

Issue: -

## Description

Checks for multiple messages stubbed on the same object.

## Examples

```ruby
# bad
before do
  allow(Service).to receive(:foo).and_return(bar)
  allow(Service).to receive(:baz).and_return(qux)
end

# good
before do
  allow(Service).to receive_messages(foo: bar, baz: qux)
end

# good - ignore same message
before do
  allow(Service).to receive(:foo).and_return(bar)
  allow(Service).to receive(:foo).and_return(qux)
end
```

## Further Reading

* [RSpec - RSpec/ReceiveMessages](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecreceivemessages)
