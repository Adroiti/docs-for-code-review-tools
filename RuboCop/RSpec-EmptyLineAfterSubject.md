Pattern: Missing empty line after `subject`

Issue: -

## Description

Checks if there is an empty line after `subject` block.

## Examples

```ruby
# bad
subject(:obj) { described_class }
let(:foo) { bar }

# good
subject(:obj) { described_class }

let(:foo) { bar }
```

## Further Reading

* [RSpec - RSpec/EmptyLineAfterSubject](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecemptylineaftersubject)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterSubject](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/EmptyLineAfterSubject)
