Pattern: Missing empty line after example group

Issue: -

## Description

Checks if there is an empty line after example group blocks.

## Examples

```ruby
# bad
RSpec.describe Foo do
  describe '#bar' do
  end
  describe '#baz' do
  end
end

# good
RSpec.describe Foo do
  describe '#bar' do
  end

  describe '#baz' do
  end
end
```

## Further Reading

* [RSpec - RSpec/EmptyLineAfterExampleGroup](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecemptylineafterexamplegroup)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterExampleGroup](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterExampleGroup)
