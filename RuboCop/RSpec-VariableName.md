Pattern: Malformed memoized helper name

Issue: -

## Description

Checks that memoized helper names use the configured style.

## Examples

```ruby
# bad
let(:userName) { 'Adam' }
subject(:userName) { 'Adam' }

# good
let(:user_name) { 'Adam' }
subject(:user_name) { 'Adam' }
```

## Further Reading

* [RSpec - RSpec/VariableName](https://docs.rubocop.org/rubocop-rspec/cops_rspec.adoc#rspecvariablename)