Pattern: Incorrect pluralization grammar

Issue: -

## Description

This rule checks for correct grammar when using ActiveSupport's core extensions to the numeric classes.

## Examples

```ruby
# bad
3.day.ago
1.months.ago

# good
3.days.ago
1.month.ago
```

## Further Reading

* [RuboCop - Rails/PluralizationGrammar](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railspluralizationgrammar)
