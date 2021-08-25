Pattern: Rrepeated describe and context block body

Issue: -

## Description

Check for repeated describe and context block body.

## Examples

```ruby
# bad
describe 'cool feature x' do
  it { cool_predicate }
end

describe 'cool feature y' do
  it { cool_predicate }
end

# good
describe 'cool feature' do
  it { cool_predicate }
end

describe 'another cool feature' do
  it { another_predicate }
end

# good
context 'when case x', :tag do
  it { cool_predicate }
end

context 'when case y' do
  it { cool_predicate }
end
```

## Further Reading

* [RSpec - RSpec/RepeatedExampleGroupBody](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecrepeatedexamplegroupbody)
