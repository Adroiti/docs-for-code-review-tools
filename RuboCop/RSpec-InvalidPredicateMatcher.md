Pattern: Invalid predicate matcher

Issue: -

## Description

Checks invalid usage for predicate matcher.

Predicate matcher does not need a question. This rule checks an unnecessary question in predicate matcher.

## Examples

```ruby
# bad
expect(foo).to be_something?

# good
expect(foo).to be_something
```

## Further Reading

* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/InvalidPredicateMatcher](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/InvalidPredicateMatcher)
