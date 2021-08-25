Pattern: Misaligned left `let` brace

Issue: -

## Description

Checks that left braces for adjacent single line `let`s are aligned.

## Examples

```ruby
# bad
let(:foobar) { blahblah }
let(:baz) { bar }
let(:a) { b }

# good
let(:foobar) { blahblah }
let(:baz)    { bar }
let(:a)      { b }
```

## Further Reading

* [RSpec - RSpec/AlignLeftLetBrace](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecalignleftletbrace)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AlignLeftLetBrace](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/AlignLeftLetBrace)
