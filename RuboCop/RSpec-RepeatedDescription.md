Pattern: Repeated description string in example group

Issue: -

## Description

Checks for repeated description strings in example groups.

## Examples

```ruby
# bad
RSpec.describe User do
  it 'is valid' do
    # ...
  end

  it 'is valid' do
    # ...
  end
end

# good
RSpec.describe User do
  it 'is valid when first and last name are present' do
    # ...
  end

  it 'is valid when last name only is present' do
    # ...
  end
end
```

## Further Reading

* [RSpec - RSpec/RepeatedDescription](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecrepeateddescription)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/RepeatedDescription](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/RepeatedDescription)
