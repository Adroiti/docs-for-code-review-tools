Pattern: Misaligned right `let` brace

Issue: -

## Description

Checks that right braces for adjacent single line `let`s are aligned.

## Examples

```ruby
# bad
let(:foobar) { blahblah }
let(:baz)    { bar }
let(:a)      { b }

# good
let(:foobar) { blahblah }
let(:baz)    { bar      }
let(:a)      { b        }
```

## Further Reading

* [RSpec - RSpec/AlignRightLetBrace](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecalignrightletbrace)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AlignRightLetBrace](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AlignRightLetBrace)
