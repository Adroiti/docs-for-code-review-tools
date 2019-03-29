Pattern: Repeated example within example group

Issue: -

## Description

Checks for repeated examples within example groups.

## Examples

```ruby
it 'is valid' do
  expect(user).to be_valid
end

it 'validates the user' do
  expect(user).to be_valid
end
```

## Further Reading

* [RSpec - RSpec/RepeatedExample](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecrepeatedexample)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/RepeatedExample](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/RepeatedExample)
