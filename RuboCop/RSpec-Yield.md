Pattern: Missing use of `.and_yield`

Issue: -

## Description

This rule checks for calling a block within a stub.

## Examples

```ruby
# bad
allow(foo).to receive(:bar) { |&block| block.call(1) }

# good
expect(foo).to be(:bar).and_yield(1)
```

## Further Reading

* [RSpec - RSpec/Yield](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecyield)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Yield](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Yield)
