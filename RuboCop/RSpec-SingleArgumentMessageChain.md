Pattern: Single-argument message chain

Issue: -

## Description

Checks that chains of messages contain more than one element.

## Examples

```ruby
# bad
allow(foo).to receive_message_chain(:bar).and_return(42)

# good
allow(foo).to receive(:bar).and_return(42)

# also good
allow(foo).to receive(:bar, :baz)
allow(foo).to receive("bar.baz")
```

## Further Reading

* [RSpec - RSpec/SingleArgumentMessageChain](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecsingleargumentmessagechain)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SingleArgumentMessageChain](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SingleArgumentMessageChain)
