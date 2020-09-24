Pattern: Repeated include example

Issue: -

## Description

Checks for repeated include of shared examples.

## Examples

```ruby
# bad
describe 'foo' do
  include_examples 'cool stuff'
  include_examples 'cool stuff'
end

# bad
describe 'foo' do
  it_behaves_like 'a cool', 'thing'
  it_behaves_like 'a cool', 'thing'
end

# bad
context 'foo' do
  it_should_behave_like 'a duck'
  it_should_behave_like 'a duck'
end

# good
describe 'foo' do
  include_examples 'cool stuff'
end

describe 'bar' do
  include_examples 'cool stuff'
end

# good
describe 'foo' do
  it_behaves_like 'a cool', 'thing'
  it_behaves_like 'a cool', 'person'
end

# good
context 'foo' do
  it_should_behave_like 'a duck'
  it_should_behave_like 'a goose'
end
```

## Further Reading

* [RSpec - RSpec/RepeatedIncludeExample](https://docs.rubocop.org/rubocop/cops_rspec.html#rspecrepeatedincludeexample)