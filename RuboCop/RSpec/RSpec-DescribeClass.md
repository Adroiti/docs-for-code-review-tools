Pattern: Malformed first `describe` argument

Issue: -

## Description

Checks that the first argument to the top level describe is a constant.

## Examples

```ruby
# bad
describe 'Do something' do
end

# good
describe TestedClass do
end

describe "A feature example", type: :feature do
end
```

## Further Reading

* [RSpec - RSpec/DescribeClass](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecdescribeclass)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribeClass](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/DescribeClass)
