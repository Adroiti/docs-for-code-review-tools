Pattern: Rails/PluralizationGrammar

Issue: -

## Description

This cop checks for correct grammar when using ActiveSupport's
core extensions to the numeric classes.

### Example

```ruby
# bad
3.day.ago
1.months.ago

# good
3.days.ago
1.month.ago
```

## Further Reading

* [RuboCop - Rails/PluralizationGrammar](https://rubocop.readthedocs.io/en/latest/cops_rails/#railspluralizationgrammar)
