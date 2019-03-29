Pattern: Missing use of `once`/`twice`

Issue: -

## Description

Checks for `once` and `twice` receive counts matchers usage.

## Examples

```ruby
# bad
expect(foo).to receive(:bar).exactly(1).times
expect(foo).to receive(:bar).exactly(2).times
expect(foo).to receive(:bar).at_least(1).times
expect(foo).to receive(:bar).at_least(2).times
expect(foo).to receive(:bar).at_most(1).times
expect(foo).to receive(:bar).at_most(2).times

# good
expect(foo).to receive(:bar).once
expect(foo).to receive(:bar).twice
expect(foo).to receive(:bar).at_least(:once)
expect(foo).to receive(:bar).at_least(:twice)
expect(foo).to receive(:bar).at_most(:once)
expect(foo).to receive(:bar).at_most(:twice).times
```

## Further Reading

* [RSpec - RSpec/ReceiveCounts](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecreceivecounts)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ReceiveCounts](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ReceiveCounts)
