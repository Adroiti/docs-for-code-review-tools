Pattern: Duplicated metadata

Issue: -

## Description

Avoid duplicated metadata.

## Examples

```ruby
# bad
describe 'Something', :a, :a

# good
describe 'Something', :a
```

## Further Reading

* [RSpec - RSpec/DuplicatedMetadata](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecduplicatedmetadata)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DuplicatedMetadata