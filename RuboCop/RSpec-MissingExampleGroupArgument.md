Pattern: Missing first argument for example group

Issue: -

## Description

Checks that the first argument to an example group is not empty.

## Examples

```ruby
# bad
describe do
end

RSpec.describe do
end

# good
describe TestedClass do
end

describe "A feature example" do
end
```

## Further Reading

* [RSpec - RSpec/MissingExampleGroupArgument](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecmissingexamplegroupargument)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MissingExampleGroupArgument](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/MissingExampleGroupArgument)
