Pattern: Attribute defined statically

Issue: -

## Description

Always declare attribute values as blocks.

## Examples

```ruby
# bad
kind [:active, :rejected].sample

# good
kind { [:active, :rejected].sample }

# bad
closed_at 1.day.from_now

# good
closed_at { 1.day.from_now }

# bad
count 1

# good
count { 1 }
```

## Further Reading

* [RSpec - FactoryBot/AttributeDefinedStatically](https://docs.rubocop.org/rubocop-rspec/cops_rspec_factorybot.html#rspecfactorybot/attributedefinedstatically)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FactoryBot/AttributeDefinedStatically](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FactoryBot/AttributeDefinedStatically)
