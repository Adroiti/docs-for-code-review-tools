Pattern: Scattered `let`

Issue: -

## Description

Checks for `let` scattered across the example group. Group lets together.

## Examples

```ruby
# bad
describe Foo do
  let(:foo) { 1 }
  subject { Foo }
  let(:bar) { 2 }
  before { prepare }
  let!(:baz) { 3 }
end

# good
describe Foo do
  subject { Foo }
  before { prepare }
  let(:foo) { 1 }
  let(:bar) { 2 }
  let!(:baz) { 3 }
end
```

## Further Reading

* [RSpec - RSpec/ScatteredLet](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecscatteredlet)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ScatteredLet](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ScatteredLet)
