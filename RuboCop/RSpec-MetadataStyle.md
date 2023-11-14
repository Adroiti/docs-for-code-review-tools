Pattern: Inconsistent metadata style

Issue: -

## Description

Checks for consistent metadata style.

## Examples

### EnforcedStyle: symbol (default)

```ruby
# bad
describe 'Something', a: true

# good
describe 'Something', :a
```

#### EnforcedStyle: hash

```ruby
# bad
describe 'Something', :a

# good
describe 'Something', a: true
```

## Further Reading

* [RSpec - RSpec/MetadataStyle](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecmetadatastyle)
