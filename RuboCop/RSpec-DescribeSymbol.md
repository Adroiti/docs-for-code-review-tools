Pattern: Use of describing symbol

Issue: -

## Description

Avoid describing symbols.

## Examples

```ruby
# bad
describe :my_method do
  # ...
end

# good
describe '#my_method' do
  # ...
end
```

## Further Reading

* [RSpec - RSpec/DescribeSymbol](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecdescribesymbol)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribeSymbol](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribeSymbol)
