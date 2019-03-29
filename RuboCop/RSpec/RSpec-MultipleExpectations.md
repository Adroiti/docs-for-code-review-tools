Pattern: Too many `expect` calls in example

Issue: -

## Description

Checks if examples contain too many `expect` calls.

This rule is configurable using the `Max` option.

## Examples

```ruby
# bad
describe UserCreator do
  it 'builds a user' do
    expect(user.name).to eq("John")
    expect(user.age).to eq(22)
  end
end

# good
describe UserCreator do
  it 'sets the users name' do
    expect(user.name).to eq("John")
  end

  it 'sets the users age' do
    expect(user.age).to eq(22)
  end
end
```
#### configuration

```ruby
# .rubocop.yml
# RSpec/MultipleExpectations:
#   Max: 2

# not flagged by rubocop
describe UserCreator do
  it 'builds a user' do
    expect(user.name).to eq("John")
    expect(user.age).to eq(22)
  end
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `1` | Integer
AggregateFailuresByDefault | `false` | Boolean

## Further Reading

* [RSpec - RSpec/MultipleExpectations](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecmultipleexpectations)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MultipleExpectations](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MultipleExpectations)
