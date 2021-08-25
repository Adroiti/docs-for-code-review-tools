Pattern: Stubbed message chain

Issue: -

## Description

Checks that chains of messages are not being stubbed.

## Examples

```ruby
# bad
allow(foo).to receive_message_chain(:bar, :baz).and_return(42)

# better
thing = Thing.new(baz: 42)
allow(foo).to receive(bar: thing)
```

## Further Reading

* [RSpec - RSpec/MessageChain](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmessagechain)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MessageChain](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MessageChain)
