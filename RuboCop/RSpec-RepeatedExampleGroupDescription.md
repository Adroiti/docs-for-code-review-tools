Pattern: Repeated example group description

Issue: -

## Description

Check for repeated example group descriptions.

## Examples

```ruby
# bad
describe 'cool feature' do
  # example group
end

describe 'cool feature' do
  # example group
end

# bad
context 'when case x' do
  # example group
end

describe 'when case x' do
  # example group
end

# good
describe 'cool feature' do
  # example group
end

describe 'another cool feature' do
  # example group
end

# good
context 'when case x' do
  # example group
end

context 'when another case' do
  # example group
end
```

## Further Reading

* [RSpec - RSpec/RepeatedExampleGroupDescription](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecrepeatedexamplegroupdescription)
