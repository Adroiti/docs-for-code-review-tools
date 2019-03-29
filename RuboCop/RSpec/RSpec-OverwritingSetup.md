Pattern: Overwriting `let`/`subject`

Issue: -

## Description

Checks if there is a `let`/`subject` that overwrites an existing one.

## Examples

```ruby
# bad
let(:foo) { bar }
let(:foo) { baz }

subject(:foo) { bar }
let(:foo) { baz }

let(:foo) { bar }
let!(:foo) { baz }

# good
subject(:test) { something }
let(:foo) { bar }
let(:baz) { baz }
let!(:other) { other }
```

## Further Reading

* [RSpec - RSpec/OverwritingSetup](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecoverwritingsetup)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/OverwritingSetup](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/OverwritingSetup)
