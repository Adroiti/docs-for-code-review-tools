Pattern: Scattered test setup

Issue: -

## Description

Checks for setup scattered across multiple hooks in an example group.

Unify `before`, `after`, and `around` hooks when possible.

## Examples

```ruby
# bad
describe Foo do
  before { setup1 }
  before { setup2 }
end

# good
describe Foo do
  before do
    setup1
    setup2
  end
end
```

## Further Reading

* [RSpec - RSpec/ScatteredSetup](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecscatteredsetup)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ScatteredSetup](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ScatteredSetup)
