Pattern: Missing empty line after final `let`

Issue: -

## Description

Checks if there is an empty line after the last `let` block.

## Examples

```ruby
# bad
let(:foo) { bar }
let(:something) { other }
it { does_something }

# good
let(:foo) { bar }
let(:something) { other }

it { does_something }
```

## Further Reading

* [RSpec - RSpec/EmptyLineAfterFinalLet](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecemptylineafterfinallet)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterFinalLet](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterFinalLet)
