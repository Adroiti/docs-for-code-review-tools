Pattern: Wrong RSpec metadata order

Issue: -

## Description

Sort RSpec metadata alphabetically.

## Examples

```ruby
# bad
describe 'Something', :b, :a
context 'Something', foo: 'bar', baz: true
it 'works', :b, :a, foo: 'bar', baz: true

# good
describe 'Something', :a, :b
context 'Something', baz: true, foo: 'bar'
it 'works', :a, :b, baz: true, foo: 'bar'
```

## Further Reading

* [RSpec - RSpec/SortMetadata](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecsortmetadata)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/SortMetadata