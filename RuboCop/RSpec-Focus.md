Pattern: Focused spec

Issue: -

## Description

Checks if examples are focused.

## Examples

```ruby
# bad
describe MyClass, focus: true do
end

describe MyClass, :focus do
end

fdescribe MyClass do
end

# good
describe MyClass do
end
```

## Further Reading

* [RSpec - RSpec/Focus](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecfocus)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Focus](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Focus)
